---
title: ".NET マイクロサービス。 コンテナー化された .NET アプリケーションのアーキテクチャ"
description: ".NET マイクロサービス: コンテナー化された .NET アプリケーションのアーキテクチャ | Front Matter"
keywords: "Docker, マイクロサービス, ASP.NET, コンテナー"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.translationtype: HT
ms.sourcegitcommit: 9bb64ea7199f5699ff166d1affb7f8126dcc6612
ms.openlocfilehash: 4307c21f32e914118c03393be7ed7a632c7a7f0b
ms.contentlocale: ja-jp
ms.lasthandoff: 09/05/2017

---

![](./media/cover.png)

# <a name="net-microservices-architecture-for-containerized-net-applications"></a>.NET マイクロサービス。 コンテナー化された .NET アプリケーションのアーキテクチャ

ダウンロード: <https://aka.ms/microservicesebook>

発行者

Microsoft 開発部門、.NET および Visual Studio 製品チーム

A division of Microsoft Corporation

One Microsoft Way

Redmond, Washington 98052-6399

Copyright © 2017 by Microsoft Corporation

All rights reserved. 本書のいかなる部分も、書面による発行者の許可なしに、いかなる形式または方法によっても、複製または伝送することを禁じます。

本書は "現状有姿" で提供され、著者の見解と意見を表しています。 URL および他の参照されているインターネットの Web サイトをはじめ、本書に記載されている見解、意見、および情報は、通知なく変更されることがあります。

ここに記載したいくつかの例は、説明のためだけに提供された架空のものです。 実在のものとの関連性または関係性は一切ありません。

http://www.microsoft.com の "商標" Web ページに記載されている Microsoft および商標は、Microsoft グループの商標です。

Mac および macOS は Apple Inc. の商標です。

Docker のクジラのロゴは Docker, Inc. の登録商標です。許可を得て使用しています。

その他のすべてのマークおよびロゴは、該当する各社が所有しています。

共同作成者:

> **Cesar de la Torre**、Microsoft corp.、.NET 製品チーム、シニア PM
>
> **Bill Wagner**、Microsoft Corp.、C+E、シニア コンテンツ開発者
>
> **Mike Rousos**、Microsoft、DevDiv CAT チーム、主任ソフトウェア エンジニア

編集者:

> **Mike Pope**
>
> **Steve Hoag**

参加者とレビュー担当者:

> **Jeffrey Ritcher**、Microsoft、Azure チーム、パートナー ソフトウェア エンジニア
>
> **Jimmy Bogard**、Headspring のチーフ アーキテクト
>
> **Udi Dahan**、Particular Software、創設者兼最高経営責任者
>
> **Jimmy Nilsson**、Factor10 の共同創始者兼最高経営責任者
>
> **Glenn Condron**、ASP.NET チーム、シニア プログラム マネージャー
>
> **Mark Fussell**、Microsoft、Azure Service Fabric チーム、プリンシパル PM リーダー
>
> **Diego Vega**、Microsoft、Entity Framework チーム、PM リーダー
>
> **Barry Dorrans**、シニア セキュリティ プログラム マネージャー
>
> **Rowan Miller**、Microsoft、シニア プログラム マネージャー
>
> **Ankit Asthana**、Microsoft、.NET チーム、主任 PM マネージャー
>
> **Scott Hunter**、Microsoft、.NET チーム、パートナー ディレクター PM
>
> **Dylan Reisenberger**、Polly のアーキテクト兼開発リーダー
>
> **Steve Smith**、ASPSmith Ltd. のソフトウェア設計者兼トレーナー
>
> **Ian Cooper**、Brighter のコーディング アーキテクト
>
> **Unai Zorrilla**、Plain Concepts のアーキテクト兼開発リーダー
>
> **Eduard Tomas**、Plain Concepts の開発リーダー
>
> **Ramon Tomas**、Plain Concepts の開発者
>
> **David Sanz**、Plain Concepts の開発者
>
> **Javier Valero**、Grupo Solutio の最高執行責任者
>
> **Pierre Millet**、Microsoft、シニア コンサルタント
>
> **Michael Friis**、Docker Inc、製品マネージャー
>
> **Charles Lowell**、Microsoft、VS CAT チーム、ソフトウェア エンジニア

## <a name="introduction"></a>はじめに

企業は、コンテナーを使用して、コストの節減、展開の問題の解決、および DevOps と製造作業の向上を実現しつつあります。 Microsoft では、Azure Container Service や Azure Service Fabric などの製品を作成したり、Docker、Mesosphere、Kubernetes などの業界リーダーと提携することで、Windows および Linux 用のコンテナーの新技術をリリースしています。 これらの製品は、企業が使用しているプラットフォームやツールに関係なく、クラウドの速度とスケールでアプリケーションを構築および展開することに役立つコンテナー ソリューションを提供します。

Docker は、コンテナー業界では事実上の標準になりつつあり、Windows と Linux のエコシステムで最も重要なベンダーでサポートされています  (Microsoft は Docker をサポートする主要なクラウド ベンダーの 1 つです)。将来、Docker は、クラウドまたはオンプレミスのあらゆるデータセンターで広く使用されるようになるでしょう。

さらに、ミッション クリティカルな分散アプリケーションのための重要なアプローチとして、[マイクロサービス](https://martinfowler.com/articles/microservices.html) アーキテクチャが新たに出現しています。 マイクロサービス ベースのアーキテクチャでは、個別に開発、テスト、展開、およびバージョン管理が可能なサービスのコレクションに基づいてアプリケーションが構築されます。

## <a name="about-this-guide"></a>このガイドについて

このガイドでは、マイクロサービス ベースのアプリケーションの開発とコンテナーを使用してこれらを管理する方法を紹介します。 .NET Core と Docker のコンテナーを使用したアーキテクチャの設計と実装アプローチについて説明します。 コンテナーとマイクロサービスの使用の開始を容易にするため、このガイドでは、ユーザーが探究できる参照コンテナー化されたマイクロサービス ベースのアプリケーションに重点を置いています。 サンプル アプリケーションは、[eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) GitHub リポジトリから入手できます。

このガイドでは、主に開発環境レベルで、Docker と .NET Core の 2 つのテクノロジに重点を置いた、基本的な開発とアーキテクチャに関するガイダンスを提供します。 このガイドは、運用環境のインフラストラクチャ (クラウドまたはオンプレミス) を重視することなく、アプリケーションの設計について考慮する際にお読みいただくことを意図しています。 インフラストラクチャに関する決定は、後で実稼働可能なアプリケーションを作成するときに行います。 そのため、このガイドは、インフラストラクチャに依存しない、より開発環境中心としたものになることを意図しています。

このガイドで学習したら、次の段階は Microsoft Azure での実稼働可能なマイクロサービスについて学習することです。

## <a name="what-this-guide-does-not-cover"></a>このガイドに含まれないもの

このガイドでは、アプリケーションのライフサイクル、DevOps、CI/CD パイプライン、またはチーム作業については詳しく取り上げません。 これらについては、補完ガイド「[Microsoft プラットフォームとツールでコンテナー化された Docker アプリケーションのライフサイクル](https://aka.ms/dockerlifecycleebook)」で詳しく説明しています。 最新のガイドでも、特定のオーケストレーターに関する情報など、Azure インフラストラクチャでの実装の詳細は提供されません。

### <a name="additional-resources"></a>その他の技術情報

-   **Microsoft プラットフォームとツールでコンテナー化された Docker アプリケーションのライフサイクル** (ダウンロード可能な電子ブック) [*https://aka.ms/dockerlifecycleebook*](https://aka.ms/dockerlifecycleebook)

## <a name="who-should-use-this-guide"></a>対象読者

このガイドは、Docker ベースのアプリケーションの開発とマイクロサービス ベースのアーキテクチャに詳しくない開発者およびソリューション設計者を対象にしています。 このガイドは、Microsoft 開発テクノロジ (特に .NET Core を中心とした) と Docker コンテナーを使用して、概念実証アプリケーションの設計、デザインおよび実装する方法を学習したい人向けに書かれています。

新しいモダンな分散アプリケーションにどのアプローチを選択するかを決定する前に、アーキテクチャとテクノロジーの概要を必要とする、エンタープライズ アーキテクトなどの技術的意思決定者にもこのガイドは役立ちます。

### <a name="how-to-use-this-guide"></a>このガイドの使用方法

このガイドの最初の部分では、Docker コンテナーを紹介し、開発フレームワークとして .NET Core または .NET Framework を選択する方法について説明し、マイクロサービスの概要を説明します。 このコンテンツは、概要は知りたいが、コード実装の詳細について詳しく知る必要がないアーキテクトおよび技術的意思決定者向けです。

ガイドの 2 番目の部分は、「[Docker ベースのアプリケーションの開発プロセス](#ch_dev_process_for_docker_based_apps)」セクションから始まります。 これは、.NET Core と Docker を使用してアプリケーションを実装するための開発とマイクロ サービスのパターンを中心に説明します。 これは、コード、パターンおよび実装の詳細を重視する開発者やアーキテクトにとって最も関心が高いセクションです。

## <a name="related-microservice-and-container-based-reference-application-eshoponcontainers"></a>関連するマイクロサービスとコンテナー ベースの参照アプリケーション: eShopOnContainers

eShopOnContainers アプリケーションは、.NET Core および Docker コンテナーを使用して展開するように設計されたマイクロサービスのための参照アプリです。 アプリケーションは、いくつかの e ストア UI フロント エンド (Web アプリとネイティブ モバイル アプリ) を含む複数のサブシステムで構成されます。 また、バック エンドのマイクロサービスと必要なサーバー側のすべての操作のためのコンテナーも含まれています。

このマイクロ サービスとコンテナー ベースのアプリケーション ソース コードは、オープン ソースで、[eShopOnContainers](http://aka.ms/MicroservicesArchitecture) GitHub リポジトリから入手できます。

## <a name="send-us-your-feedback"></a>フィードバックをお寄せください。

このガイドは、コンテナー化されたアプリケーションと .NET のマイクロサービスのアーキテクチャの理解を促進する目的で書かれています。 ガイドと関連する参照アプリケーションは進化していくため、お客様のフィードバックをお待ちしています。 このガイドを改善する方法についてご意見があれば、以下のアドレスに送信してください。

[dotnet-architecture-ebooks-feedback@service.microsoft.com](mailto:dotnet-architecture-ebooks-feedback@service.microsoft.com)

>[!div class="step-by-step"]
[次へ] (container-docker-introduction/index.md)
