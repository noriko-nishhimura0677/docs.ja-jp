---
title: サーバーレス アーキテクチャの考慮事項 - サーバーレス アプリ
description: ログ、トレースと診断の状態の管理とスケールには、永続的なストレージからのサーバーレス アプリケーションの設計の課題を理解します。
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 5f175351cf42f3d9966add72750d64a4efe14e07
ms.sourcegitcommit: bd4fa78f5a46133efdead1bc692a9aa2811d7868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/23/2018
ms.locfileid: "49370275"
---
# <a name="serverless-architecture-considerations"></a><span data-ttu-id="18802-103">サーバーレス アーキテクチャの考慮事項</span><span class="sxs-lookup"><span data-stu-id="18802-103">Serverless architecture considerations</span></span>

<span data-ttu-id="18802-104">サーバーレス アーキテクチャを採用することはいくつかの課題に付属します。</span><span class="sxs-lookup"><span data-stu-id="18802-104">Adopting a serverless architecture does come with certain challenges.</span></span> <span data-ttu-id="18802-105">このセクションでは、いくつかの注意すべき一般的な考慮事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="18802-105">This section explores some of the more common considerations to be aware of.</span></span> <span data-ttu-id="18802-106">これらの課題のすべてで、ソリューションがあります。</span><span class="sxs-lookup"><span data-stu-id="18802-106">All of these challenges have solutions.</span></span> <span data-ttu-id="18802-107">すべてのアーキテクチャの選択肢と同様、長所と短所を慎重に検討した後でのみサーバーレスに移行するかどうかを行ってください。</span><span class="sxs-lookup"><span data-stu-id="18802-107">As with all architecture choices, the decision to go serverless should be made only after carefully considering the pros and cons.</span></span> <span data-ttu-id="18802-108">アプリケーションのニーズに応じてサーバーレスの実装を特定のコンポーネントの適切なソリューションではないことができます。</span><span class="sxs-lookup"><span data-stu-id="18802-108">Depending on the needs of your application, you may decide a serverless implementation isn't the right solution for certain components.</span></span>

## <a name="managing-state"></a><span data-ttu-id="18802-109">状態を管理します。</span><span class="sxs-lookup"><span data-stu-id="18802-109">Managing state</span></span>

<span data-ttu-id="18802-110">サーバーレス関数は、一般に、マイクロ サービスと同様、既定でステートレスなは。</span><span class="sxs-lookup"><span data-stu-id="18802-110">Serverless functions, as with microservices in general, are stateless by default.</span></span> <span data-ttu-id="18802-111">状態の回避は、一時的な障害の中心点のない回復性を提供して、スケール アウトするサーバーレスできます。</span><span class="sxs-lookup"><span data-stu-id="18802-111">Avoiding state enables serverless to be ephemeral, to scale out, and to provide resiliency without a central point of failure.</span></span> <span data-ttu-id="18802-112">いくつかの状況では、ビジネス プロセスには、状態が必要があります。</span><span class="sxs-lookup"><span data-stu-id="18802-112">In some circumstances, business processes require state.</span></span> <span data-ttu-id="18802-113">プロセスには、状態が必要とする場合は、2 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="18802-113">If your process requires state, you have two options.</span></span> <span data-ttu-id="18802-114">サーバーレス、以外のモデルを採用したり、状態を提供する個別のサービスと対話できます。</span><span class="sxs-lookup"><span data-stu-id="18802-114">You can adopt a model other than serverless, or interact with a separate service that provides state.</span></span> <span data-ttu-id="18802-115">状態を追加すると、ソリューションが複雑になることができますと、スケール、厄介なし、単一障害点が作成される可能性が。</span><span class="sxs-lookup"><span data-stu-id="18802-115">Adding state can complicate the solution and make it harder to scale, and potentially create a single point of failure.</span></span> <span data-ttu-id="18802-116">関数が、状態を絶対に必要かどうかを慎重に検討します。</span><span class="sxs-lookup"><span data-stu-id="18802-116">Carefully consider whether your function absolutely requires state.</span></span> <span data-ttu-id="18802-117">答えが"yes"の場合は、かどうかも、サーバーレスでこれを実装することを決定します。</span><span class="sxs-lookup"><span data-stu-id="18802-117">If the answer is "yes," determine whether it still makes sense to implement it with serverless.</span></span>

<span data-ttu-id="18802-118">サーバーレスのメリットを損なうことがなく状態を採用するいくつかのソリューションがあります。</span><span class="sxs-lookup"><span data-stu-id="18802-118">There are several solutions to adopt state without compromising the benefits of serverless.</span></span> <span data-ttu-id="18802-119">最も一般的なソリューションをいくつか挙げます。</span><span class="sxs-lookup"><span data-stu-id="18802-119">Some of the more popular solutions include:</span></span>

* <span data-ttu-id="18802-120">一時的なデータ ストアまたは Redis のように、分散キャッシュを使用します。</span><span class="sxs-lookup"><span data-stu-id="18802-120">Use a temporary data store or distributed cache, like Redis</span></span>
* <span data-ttu-id="18802-121">SQL または cosmos Db のように、データベースの状態を保存します。</span><span class="sxs-lookup"><span data-stu-id="18802-121">Store state in a database, like SQL or CosmosDB</span></span>
* <span data-ttu-id="18802-122">Durable functions のようなワークフロー エンジンを介して状態を処理します。</span><span class="sxs-lookup"><span data-stu-id="18802-122">Handle state through a workflow engine like durable functions</span></span>

<span data-ttu-id="18802-123">一番下の行は、サーバーレスで実装することを検討しているプロセス内で、状態管理の必要性を把握しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="18802-123">The bottom line is that you should be aware of the need for any state management within processes you're considering to implement with serverless.</span></span>

## <a name="long-running-processes"></a><span data-ttu-id="18802-124">実行時間の長いプロセス</span><span class="sxs-lookup"><span data-stu-id="18802-124">Long-running processes</span></span>

<span data-ttu-id="18802-125">サーバーレスの多くのメリットは、一時的なプロセスに依存します。</span><span class="sxs-lookup"><span data-stu-id="18802-125">Many benefits of serverless rely on the processes being ephemeral.</span></span> <span data-ttu-id="18802-126">実行時間の短いやすく、サーバーレスのプロバイダーのホスト間で関数の関数が終了し、共有リソースを解放します。</span><span class="sxs-lookup"><span data-stu-id="18802-126">Short run times make it easier for the serverless provider to free up resources as functions end and share functions across hosts.</span></span> <span data-ttu-id="18802-127">ほとんどのクラウド プロバイダーでは、約 10 分間に、関数を実行できる合計時間を制限します。</span><span class="sxs-lookup"><span data-stu-id="18802-127">Most cloud providers limit the total time your function can run to around 10 minutes.</span></span> <span data-ttu-id="18802-128">プロセスがかかる場合があります、代替実装を検討する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="18802-128">If your process may take longer, you might consider an alternative implementation.</span></span>

<span data-ttu-id="18802-129">いくつかの例外とソリューションがあります。</span><span class="sxs-lookup"><span data-stu-id="18802-129">There are a few exceptions and solutions.</span></span> <span data-ttu-id="18802-130">1 つのソリューションは、個別にかかる実行時間がより小さなコンポーネントに、プロセスを中断する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="18802-130">One solution may be to break your process into smaller components that individually take less time to run.</span></span> <span data-ttu-id="18802-131">依存関係の時間の長いため、プロセスを実行する場合は、durable functions のようなソリューションを使用して非同期ワークフローも検討できます。</span><span class="sxs-lookup"><span data-stu-id="18802-131">If your process runs long because of dependencies, you can also consider an asynchronous workflow using a solution like durable functions.</span></span> <span data-ttu-id="18802-132">Durable functions では、一時停止あり、外部の処理が完了するには、待機中に、プロセスの状態を維持します。</span><span class="sxs-lookup"><span data-stu-id="18802-132">Durable functions pause and maintain the state of your process while it's waiting on an external process to finish.</span></span> <span data-ttu-id="18802-133">非同期処理には、実際のプロセスの実行時間が短縮されます。</span><span class="sxs-lookup"><span data-stu-id="18802-133">Asynchronous handling reduces the time the actual process runs.</span></span>

## <a name="startup-time"></a><span data-ttu-id="18802-134">起動時間</span><span class="sxs-lookup"><span data-stu-id="18802-134">Startup time</span></span>

<span data-ttu-id="18802-135">サーバーレスの実装の 1 つの潜在的な問題は、スタートアップ時間です。</span><span class="sxs-lookup"><span data-stu-id="18802-135">One potential concern with serverless implementations is startup time.</span></span> <span data-ttu-id="18802-136">リソースを節約するために多くのサーバーレス プロバイダーが"、オンデマンドで"インフラストラクチャを作成します。</span><span class="sxs-lookup"><span data-stu-id="18802-136">To conserve resources, many serverless providers create infrastructure "on demand."</span></span> <span data-ttu-id="18802-137">指定した時間の経過後サーバーレスの関数がトリガーされると、関数をホストするためのリソースが作成または再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="18802-137">When a serverless function is triggered after a period of time, the resources to host the function may need to be created or restarted.</span></span> <span data-ttu-id="18802-138">場合によっては、いくつかの秒の遅延がコールド スタート可能性があります。</span><span class="sxs-lookup"><span data-stu-id="18802-138">In some situations, cold starts may result in delays of several seconds.</span></span> <span data-ttu-id="18802-139">起動時間は、プロバイダーとサービス レベルによって異なります。</span><span class="sxs-lookup"><span data-stu-id="18802-139">Startup time varies across providers and service levels.</span></span> <span data-ttu-id="18802-140">アドレス起動時間にいくつかの方法がある場合は、アプリの成功を最小化することが重要です。</span><span class="sxs-lookup"><span data-stu-id="18802-140">There are a few approaches to address startup time if it's important to minimize for the success of the app.</span></span>

* <span data-ttu-id="18802-141">一部のプロバイダーでは、インフラストラクチャは、"常に on"を保証するサービス レベルの料金を支払うようにします。</span><span class="sxs-lookup"><span data-stu-id="18802-141">Some providers allow users to pay for service levels that guarantee infrastructure is "always on".</span></span>
* <span data-ttu-id="18802-142">Keep alive メカニズム (ping"起動状態"に保つためにエンドポイント) を実装します。</span><span class="sxs-lookup"><span data-stu-id="18802-142">Implement a keep-alive mechanism (ping the endpoint to keep it "awake").</span></span>
* <span data-ttu-id="18802-143">(ホストが既に実行中の新しいインスタンスをスピンアップは非常に高速) 関数のコンテナー化されたアプローチでは、Kubernetes などのオーケストレーションを使用します。</span><span class="sxs-lookup"><span data-stu-id="18802-143">Use orchestration like Kubernetes with a containerized function approach (the host is already running so spinning up new instances is extremely fast).</span></span>

## <a name="database-updates-and-migrations"></a><span data-ttu-id="18802-144">データベースの更新と移行</span><span class="sxs-lookup"><span data-stu-id="18802-144">Database updates and migrations</span></span>

<span data-ttu-id="18802-145">サーバーレス コードの利点は、アプリケーション全体を再デプロイしなくても新しい関数を解放することができます。</span><span class="sxs-lookup"><span data-stu-id="18802-145">An advantage of serverless code is that you can release new functions without having to redeploy the entire application.</span></span> <span data-ttu-id="18802-146">この利点は、リレーショナル データベースが関係する場合、欠点になります。</span><span class="sxs-lookup"><span data-stu-id="18802-146">This advantage can become a disadvantage when there's a relational database involved.</span></span> <span data-ttu-id="18802-147">データベース スキーマへの変更はサーバーレスの更新プログラムと同期する困難です。</span><span class="sxs-lookup"><span data-stu-id="18802-147">Changes to database schemas are difficult to synchronize with serverless updates.</span></span> <span data-ttu-id="18802-148">新たな課題は、問題が生じたときに、変更をロールバックする必要がありますに挙げられています。</span><span class="sxs-lookup"><span data-stu-id="18802-148">Additional challenges are posed when things go wrong and the changes must be rolled back.</span></span> <span data-ttu-id="18802-149">データの整合性は、マイクロ サービスやサーバーレス機能のためのベスト プラクティスは、独自のデータを所有している理由の 1 つです。</span><span class="sxs-lookup"><span data-stu-id="18802-149">Data integrity is one reason that a best practice for microservices and serverless functions is that they own their own data.</span></span> <span data-ttu-id="18802-150">コンピューティングとデータの 1 つの単位として変更をデプロイできるようになります。</span><span class="sxs-lookup"><span data-stu-id="18802-150">It is possible to deploy changes as a single unit of compute and data.</span></span> <span data-ttu-id="18802-151">実際には、サーバーレス アーキテクチャと一致する必要がある大規模なバック エンド データベースの機能を多くのレガシ システムです。</span><span class="sxs-lookup"><span data-stu-id="18802-151">The reality is that many legacy systems feature a large back-end database that must be reconciled with the serverless architecture.</span></span>

<span data-ttu-id="18802-152">スキーマのバージョン管理を解決するために一般的なアプローチでは、既存のプロパティと列を変更できませんが、代わりに新しい情報を追加します。</span><span class="sxs-lookup"><span data-stu-id="18802-152">A popular approach to solve schema versioning is to never modify existing properties and columns, but instead add new information.</span></span> <span data-ttu-id="18802-153">たとえば、ブール値から移動する変更を「完了日」に todo リストのフラグを「完了」</span><span class="sxs-lookup"><span data-stu-id="18802-153">For example, consider a change to move from a Boolean "completed" flag for a todo list to a "completed date."</span></span> <span data-ttu-id="18802-154">古いフィールドを削除するには、代わりに、データベースの変更を行います。</span><span class="sxs-lookup"><span data-stu-id="18802-154">Instead of removing the old field, the database change will:</span></span>

1. <span data-ttu-id="18802-155">新しい「完了日」フィールドを追加します。</span><span class="sxs-lookup"><span data-stu-id="18802-155">Add a new "completed date" field.</span></span>
1. <span data-ttu-id="18802-156">完了した日付が現在の日付後かどうかを評価する計算された関数を「完了」のブール値フィールドを変換します。</span><span class="sxs-lookup"><span data-stu-id="18802-156">Transform the "completed" Boolean field to a computed function that evaluates whether the completed date is after the current date.</span></span>
1. <span data-ttu-id="18802-157">完了したブール値が設定されている場合、現在の日付に完了した日付を設定するトリガーの追加を true にします。</span><span class="sxs-lookup"><span data-stu-id="18802-157">Add a trigger to set the completed date to the current date when the completed Boolean is set to true.</span></span>

<span data-ttu-id="18802-158">一連の変更により、レガシ コードが引き続き新しいサーバーレス関数を利用して、新しいフィールドの中に、「現状有姿を実行します。</span><span class="sxs-lookup"><span data-stu-id="18802-158">The sequence of changes ensures that legacy code continues to run "as is" while newer serverless functions can take advantage of the new field.</span></span>

<span data-ttu-id="18802-159">サーバーレス アーキテクチャでデータの詳細については、次を参照してください。[に関する課題とソリューションの分散データ管理](../microservices-architecture/architect-microservice-container-applications/distributed-data-management.md)します。</span><span class="sxs-lookup"><span data-stu-id="18802-159">For more information about data in serverless architectures, see [Challenges and solutions for distributed data management](../microservices-architecture/architect-microservice-container-applications/distributed-data-management.md).</span></span>

## <a name="scaling"></a><span data-ttu-id="18802-160">スケーリング</span><span class="sxs-lookup"><span data-stu-id="18802-160">Scaling</span></span>

<span data-ttu-id="18802-161">サーバーレスは「サーバーはありません」よくある誤解ですが</span><span class="sxs-lookup"><span data-stu-id="18802-161">It's a common misconception that serverless means "no server."</span></span> <span data-ttu-id="18802-162">実際には"server 以下です"</span><span class="sxs-lookup"><span data-stu-id="18802-162">It's in fact "less server."</span></span> <span data-ttu-id="18802-163">あるという事実は、バッキング インフラストラクチャがスケーリングに関しては重要です。</span><span class="sxs-lookup"><span data-stu-id="18802-163">The fact there is a backing infrastructure is important to understand when it comes to scaling.</span></span> <span data-ttu-id="18802-164">最もサーバーレス プラットフォームでは、一連のイベントの密度が増えた場合で、インフラストラクチャをスケーリングする方法を処理するためにコントロールを提供します。</span><span class="sxs-lookup"><span data-stu-id="18802-164">Most serverless platforms provide a set of controls to handle how the infrastructure should scale when event density increases.</span></span> <span data-ttu-id="18802-165">さまざまなオプションから選択できますが、戦略は、関数によって異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="18802-165">You can choose from a variety of options, but your strategy may vary depending on the function.</span></span> <span data-ttu-id="18802-166">さらに、関数は、同じホスト上の関数がある、同じスケール オプションように通常、関連するホストで実行されます。</span><span class="sxs-lookup"><span data-stu-id="18802-166">Furthermore, functions are typically run under a related host, so that functions on the same host have the same scale options.</span></span> <span data-ttu-id="18802-167">そのためを整理し、顧客のどの機能がホストされているスケール要件に基づいて必要なは。</span><span class="sxs-lookup"><span data-stu-id="18802-167">Therefore it is necessary to organize and strategize which functions are hosted together based on scale requirements.</span></span>

<span data-ttu-id="18802-168">規則は多くの場合、スケール アップする方法を指定 (ホスト リソースを増やす) およびスケール アウト (ホスト インスタンスの数を増やす) さまざまなパラメーターに基づきます。</span><span class="sxs-lookup"><span data-stu-id="18802-168">Rules often specify how to scale-up (increase the host resources) and scale-out (increase the number of host instances) based on varying parameters.</span></span> <span data-ttu-id="18802-169">スケールのトリガーには、スケジュール、要求レート、CPU 使用率およびメモリ使用量を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="18802-169">Triggers for scales may include schedule, request rates, CPU utilization, and memory usage.</span></span> <span data-ttu-id="18802-170">高いパフォーマンスで多くの場合よりコストが発生します。</span><span class="sxs-lookup"><span data-stu-id="18802-170">Higher performance often comes at a greater cost.</span></span> <span data-ttu-id="18802-171">すばやくと要求レートが突然の増加に応じて、低コスト、使用量ベースのアプローチは拡張できません可能性があります。</span><span class="sxs-lookup"><span data-stu-id="18802-171">The less expensive, consumption-based approaches may not scale as quickly when the request rate suddenly increases.</span></span> <span data-ttu-id="18802-172">前もって「保険コスト」料金を支払うと支払いの間のトレードオフが厳密に"としてする go"およびリスクの需要の急激な増加のため応答が遅くなります。</span><span class="sxs-lookup"><span data-stu-id="18802-172">There is a trade-off between paying up front "insurance cost" versus paying strictly "as you go" and risking slower responses due to sudden increases in demand.</span></span>

## <a name="monitoring-tracing-and-logging"></a><span data-ttu-id="18802-173">監視、トレース、およびログ記録</span><span class="sxs-lookup"><span data-stu-id="18802-173">Monitoring, tracing, and logging</span></span>

<span data-ttu-id="18802-174">DevOps の見落とされがちな側面には、1 回配置されたアプリケーションは監視です。</span><span class="sxs-lookup"><span data-stu-id="18802-174">An often overlooked aspect of DevOps is monitoring applications once deployed.</span></span> <span data-ttu-id="18802-175">サーバーレス関数を監視するための戦略に重要です。</span><span class="sxs-lookup"><span data-stu-id="18802-175">It's important to have a strategy for monitoring serverless functions.</span></span> <span data-ttu-id="18802-176">最大の課題は、相関関係、またはユーザーが同一の相互作用の一部として複数の関数を呼び出すときに認識する多くの場合は。</span><span class="sxs-lookup"><span data-stu-id="18802-176">The biggest challenge is often correlation, or recognizing when a user calls multiple functions as part of the same interaction.</span></span> <span data-ttu-id="18802-177">最もサーバーレス プラットフォームを使用すると、コンソール ログをサード パーティのツールにインポートできます。</span><span class="sxs-lookup"><span data-stu-id="18802-177">Most serverless platforms allow console logging that can be imported into third-party tools.</span></span> <span data-ttu-id="18802-178">テレメトリの収集を自動化、生成および追跡の相関関係 Id、および詳細な情報を提供する特定のアクションを監視するためのオプションもあります。</span><span class="sxs-lookup"><span data-stu-id="18802-178">There are also options to automate collection of telemetry, generate and track correlation IDs, and monitor specific actions to provide detailed insights.</span></span> <span data-ttu-id="18802-179">Azure には、高度な[Application Insights プラットフォーム](https://docs.microsoft.com/azure/azure-functions/functions-monitoring)で監視および分析します。</span><span class="sxs-lookup"><span data-stu-id="18802-179">Azure provides the advanced [Application Insights platform](https://docs.microsoft.com/azure/azure-functions/functions-monitoring) for monitoring and analytics.</span></span>

## <a name="inter-service-dependencies"></a><span data-ttu-id="18802-180">サービス間の依存関係</span><span class="sxs-lookup"><span data-stu-id="18802-180">Inter-service dependencies</span></span>

<span data-ttu-id="18802-181">サーバーレス アーキテクチャでは、その他の関数に依存する関数を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="18802-181">A serverless architecture may include functions that rely on other functions.</span></span> <span data-ttu-id="18802-182">実際には、にない一般的でない複数サービスの相互作用または分散トランザクションの一部として相互に呼び出すサーバーレス アーキテクチャ。</span><span class="sxs-lookup"><span data-stu-id="18802-182">In fact, it isn't uncommon in a serverless architecture to have multiple services call each other as part of an interaction or distributed transaction.</span></span> <span data-ttu-id="18802-183">強力な結合を避けるためには、サービスはありませんを参照する他の直接をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="18802-183">To avoid strong coupling, it's recommended that services don't reference each other directly.</span></span> <span data-ttu-id="18802-184">サービスのエンドポイントを変更する場合の直接参照が主なリファクタリングになる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="18802-184">When the endpoint for a service needs to change, direct references could result in major refactoring.</span></span> <span data-ttu-id="18802-185">要求の種類の適切な終了点を提供する、レジストリなどのサービス検出メカニズムを提供することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="18802-185">A suggested solution is to provide a service discovery mechanism, such as a registry, that provides the appropriate end point for a request type.</span></span> <span data-ttu-id="18802-186">別のソリューションでは、サービス間の通信のキューやトピックなどのメッセージング サービスを活用します。</span><span class="sxs-lookup"><span data-stu-id="18802-186">Another solution is to leverage messaging services like queues or topics for communication between services.</span></span>

## <a name="managing-failure-and-providing-resiliency"></a><span data-ttu-id="18802-187">障害の管理と回復性を提供します。</span><span class="sxs-lookup"><span data-stu-id="18802-187">Managing failure and providing resiliency</span></span>

<span data-ttu-id="18802-188">考慮すべき重要なも、*サーキット ブレーカー パターン*: をそのサービスを繰り返し呼び出すことをお勧めいない場合、何らかの理由で、サービスは失敗が続く、します。</span><span class="sxs-lookup"><span data-stu-id="18802-188">It's also important to consider the *circuit-breaker pattern*: If, for some reason, a service continues to fail, it isn't advisable to call that service repeatedly.</span></span> <span data-ttu-id="18802-189">代わりに、別のサービスが呼び出されるか、依存サービスの正常性が再確立されるまで、メッセージが返されます。</span><span class="sxs-lookup"><span data-stu-id="18802-189">Instead, an alternative service is called or a message returned until the health of the dependent service is re-established.</span></span> <span data-ttu-id="18802-190">サーバーレス アーキテクチャでは、解決、およびサービス間の依存関係の管理の戦略を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="18802-190">The serverless architecture needs to take into account the strategy for resolving and managing inter-service dependencies.</span></span>

<span data-ttu-id="18802-191">サーキット ブレーカー パターンを続行するには、サービスはフォールト トレラントであり、回復力のあるを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="18802-191">To continue the circuit-breaker pattern, services need to be fault tolerant and resilient.</span></span> <span data-ttu-id="18802-192">フォールト トレランスは予期しない例外発生後も実行を継続するアプリケーションの機能、または無効な状態が発生しました。</span><span class="sxs-lookup"><span data-stu-id="18802-192">Fault tolerance refers to the ability of your application to continue running even after unexpected exceptions or invalid states are encountered.</span></span> <span data-ttu-id="18802-193">フォールト トレランスは、通常、コード自体の関数と、例外を処理するために記述する方法。</span><span class="sxs-lookup"><span data-stu-id="18802-193">Fault tolerance is typically a function of the code itself and how it's written to handle exceptions.</span></span> <span data-ttu-id="18802-194">回復性の障害から回復できる能力のアプリが指しています。</span><span class="sxs-lookup"><span data-stu-id="18802-194">Resiliency refers to how capable the app is at recovering from failures.</span></span> <span data-ttu-id="18802-195">回復性は、多くの場合、サーバーレス プラットフォームによって管理されます。</span><span class="sxs-lookup"><span data-stu-id="18802-195">Resiliency is often managed by the serverless platform.</span></span> <span data-ttu-id="18802-196">プラットフォームは、既存のものが失敗したときに、新しいサーバーレスの関数インスタンスを起動できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="18802-196">The platform should be able to spin up a new serverless function instance when the existing one fails.</span></span> <span data-ttu-id="18802-197">プラットフォームは、インテリジェントなすべての新しいインスタンスが失敗したときに、新しいインスタンスをスピンアップを停止する必要があります。</span><span class="sxs-lookup"><span data-stu-id="18802-197">The platform should also be intelligent enough to stop spinning up new instances when every new instance fails.</span></span>

<span data-ttu-id="18802-198">詳細については、次を参照してください。[サーキット ブレーカー パターンを実装する](../microservices-architecture/implement-resilient-applications/implement-circuit-breaker-pattern.md)します。</span><span class="sxs-lookup"><span data-stu-id="18802-198">For more information, see [Implementing the Circuit Breaker pattern](../microservices-architecture/implement-resilient-applications/implement-circuit-breaker-pattern.md).</span></span>

## <a name="versioning-and-greenblue-deployments"></a><span data-ttu-id="18802-199">バージョン管理、および緑/青の展開</span><span class="sxs-lookup"><span data-stu-id="18802-199">Versioning and green/blue deployments</span></span>

<span data-ttu-id="18802-200">サーバーなしの大きな利点は、アプリケーション全体を再デプロイしなくても、特定の関数をアップグレードする機能です。</span><span class="sxs-lookup"><span data-stu-id="18802-200">A major benefit of serverless is the ability to upgrade a specific function without having to redeploy the entire application.</span></span> <span data-ttu-id="18802-201">正常に行うアップグレードでは、関数がありますバージョン管理されたサービスを呼び出すことがコードの正しいバージョンにルーティングされるようにします。</span><span class="sxs-lookup"><span data-stu-id="18802-201">For upgrades to be successful, functions must be versioned so that services calling them are routed to the correct version of code.</span></span> <span data-ttu-id="18802-202">新しいバージョンをデプロイするための戦略も重要です。</span><span class="sxs-lookup"><span data-stu-id="18802-202">A strategy for deploying new versions is also important.</span></span> <span data-ttu-id="18802-203">一般的なアプローチは、「緑/青展開します」を使用するには</span><span class="sxs-lookup"><span data-stu-id="18802-203">A common approach is to use "green/blue deployments."</span></span> <span data-ttu-id="18802-204">グリーン配置には、現在の関数です。</span><span class="sxs-lookup"><span data-stu-id="18802-204">The green deployment is the current function.</span></span> <span data-ttu-id="18802-205">新しい「青」バージョンが運用環境にデプロイし、テストします。</span><span class="sxs-lookup"><span data-stu-id="18802-205">A new "blue" version is deployed to production and tested.</span></span> <span data-ttu-id="18802-206">パスをテストするときに、緑、青のバージョン、新しいバージョンがライブになるようにスワップされます。</span><span class="sxs-lookup"><span data-stu-id="18802-206">When testing passes, the green and blue versions are swapped so the new version comes live.</span></span> <span data-ttu-id="18802-207">問題が発生した場合戻るスワップすることができます。</span><span class="sxs-lookup"><span data-stu-id="18802-207">If any issues are encountered, they can be swapped back.</span></span> <span data-ttu-id="18802-208">バージョン管理と緑/青の展開をサポートしているバージョンの変化に対応する関数を作成および展開を処理するサーバーレス プラットフォームの操作の組み合わせが必要です。</span><span class="sxs-lookup"><span data-stu-id="18802-208">Supporting versioning and green/blue deployments requires a combination of authoring the functions to accommodate version changes and working with the serverless platform to handle deployments.</span></span> <span data-ttu-id="18802-209">これについては、プロキシを使用する方法の 1 つは、 [Azure サーバーレス プラットフォーム](azure-functions.md#proxies)」の章。</span><span class="sxs-lookup"><span data-stu-id="18802-209">One possible approach is to use proxies, which are described in the [Azure serverless platform](azure-functions.md#proxies) chapter.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="18802-210">[前へ](serverless-architecture.md)
[次へ](serverless-design-examples.md)</span><span class="sxs-lookup"><span data-stu-id="18802-210">[Previous](serverless-architecture.md)
[Next](serverless-design-examples.md)</span></span>