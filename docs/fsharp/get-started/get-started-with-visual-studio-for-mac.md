---
title: "Mac 用 Visual Studio での f# の概要します。"
description: "使用する方法をについて f# で Visual Studio for mac"
keywords: "visual f#, f#, 関数型プログラミング"
author: mizzle-mo
ms.author: phcart
ms.date: 02/13/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 8db75596-19a9-4eda-b20d-a12d517c8cc1
ms.openlocfilehash: beee874e3a549531b520d4ac2150bc10dcab7725
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="get-started-with-f-in-visual-studio-for-mac"></a><span data-ttu-id="60e67-104">Mac 用 Visual Studio での f# の概要します。</span><span class="sxs-lookup"><span data-stu-id="60e67-104">Get started with F# in Visual Studio for Mac</span></span>

<span data-ttu-id="60e67-105">F# および Visual f# ツールは、Mac の IDE の Visual Studio でサポートされます。</span><span class="sxs-lookup"><span data-stu-id="60e67-105">F# and the Visual F# tooling are supported in the Visual Studio for Mac IDE.</span></span>  <span data-ttu-id="60e67-106">作業を開始するには[Mac 用の Visual Studio のダウンロード](https://www.visualstudio.com/downloads/download-visual-studio-vs)まだ行っていない場合は、します。</span><span class="sxs-lookup"><span data-stu-id="60e67-106">To begin, you should [download Visual Studio for Mac](https://www.visualstudio.com/downloads/download-visual-studio-vs), if you haven't already.</span></span>  <span data-ttu-id="60e67-107">この記事 for Mac を Visual Studio コミュニティ 2017 を使用しますが、任意のバージョンの F# で使用することができます。</span><span class="sxs-lookup"><span data-stu-id="60e67-107">This article uses the Visual Studio Community 2017 for Mac, but you can use F# with the version of your choice.</span></span>

## <a name="installing-f"></a><span data-ttu-id="60e67-108">F# をインストールします。</span><span class="sxs-lookup"><span data-stu-id="60e67-108">Installing F#</span></span> #

<span data-ttu-id="60e67-109">Visual Studio for Mac をダウンロード後にインストールするを選択するように求められます。</span><span class="sxs-lookup"><span data-stu-id="60e67-109">After downloading Visual Studio for Mac, it will prompt you to choose what you want to install.</span></span>  <span data-ttu-id="60e67-110">この記事の目的でおはままになっている、既定値です。</span><span class="sxs-lookup"><span data-stu-id="60e67-110">For the purposes of this article we will be leaving the defaults.</span></span>  <span data-ttu-id="60e67-111">Windows 用 Visual Studio とは対照的を具体的には f# のサポートをインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="60e67-111">In contrast to Visual Studio for Windows, you do not need to specifically install F# support.</span></span>  <span data-ttu-id="60e67-112">続行するには、「インストール」キーを押します。</span><span class="sxs-lookup"><span data-stu-id="60e67-112">Press "Install" to proceed.</span></span>

<span data-ttu-id="60e67-113">インストールが完了した後は、"Visual Studio を起動する"を選択します。</span><span class="sxs-lookup"><span data-stu-id="60e67-113">After the install completes, choose "Start Visual Studio".</span></span>  <span data-ttu-id="60e67-114">起動することも、Finder から macos です。</span><span class="sxs-lookup"><span data-stu-id="60e67-114">You can also launch it through Finder on macOS.</span></span>

## <a name="creating-a-console-application"></a><span data-ttu-id="60e67-115">コンソール アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="60e67-115">Creating a console application</span></span>

<span data-ttu-id="60e67-116">Mac 用の Visual Studio での最も基本的なプロジェクトの 1 つは、コンソール アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="60e67-116">One of the most basic projects in Visual Studio for Mac is the Console Application.</span></span>  <span data-ttu-id="60e67-117">これを行う方法を次に示します。</span><span class="sxs-lookup"><span data-stu-id="60e67-117">Here's how to do it.</span></span>  <span data-ttu-id="60e67-118">Visual Studio for Mac が開くです。</span><span class="sxs-lookup"><span data-stu-id="60e67-118">Once Visual Studio for Mac is open:</span></span>

1. <span data-ttu-id="60e67-119">**ファイル** メニューのをポイント**新しいソリューション**です。</span><span class="sxs-lookup"><span data-stu-id="60e67-119">On the **File** menu, point to **New Solution**.</span></span>

2.  <span data-ttu-id="60e67-120">新しいプロジェクト ダイアログでは、コンソール アプリケーションの 2 つの異なるテンプレートがあります。</span><span class="sxs-lookup"><span data-stu-id="60e67-120">In the New Project dialog, there are 2 different templates for Console Application.</span></span>  <span data-ttu-id="60e67-121">もう 1 つである .NET、.NET Framework を対象にする]-> [です。</span><span class="sxs-lookup"><span data-stu-id="60e67-121">There is one under Other -> .NET which targets the .NET Framework.</span></span>  <span data-ttu-id="60e67-122">.NET Core では他のテンプレートは、.NET Core を対象とするアプリ]-> [です。</span><span class="sxs-lookup"><span data-stu-id="60e67-122">The other template is under .NET Core -> App which targets .NET Core.</span></span>  <span data-ttu-id="60e67-123">この記事の目的でテンプレートのいずれかで動作します。</span><span class="sxs-lookup"><span data-stu-id="60e67-123">Either template should work for the purpose of this article.</span></span>

3. <span data-ttu-id="60e67-124">コンソール アプリの場合は、c# f# を必要に応じて変更します。</span><span class="sxs-lookup"><span data-stu-id="60e67-124">Under console app, change C# to F# if needed.</span></span>  <span data-ttu-id="60e67-125">選択、**次**前方に移動するボタンです。</span><span class="sxs-lookup"><span data-stu-id="60e67-125">Choose the **Next** button to move forward!</span></span>  

4. <span data-ttu-id="60e67-126">プロジェクトの名前を指定し、アプリの必要なオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="60e67-126">Give your project a name, and choose the options you want for the app.</span></span>  <span data-ttu-id="60e67-127">プレビュー ウィンドウに作成されるディレクトリ構造を表示する画面の端に通知することは、選択したオプションに基づいています。</span><span class="sxs-lookup"><span data-stu-id="60e67-127">Notice, the preview pane to the side of the screen that will show the directory structure that will be created based on the options selected.</span></span>  

5. <span data-ttu-id="60e67-128">
              **[作成]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="60e67-128">Click **Create**.</span></span>  <span data-ttu-id="60e67-129">ソリューション エクスプ ローラーで f# プロジェクトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="60e67-129">You should now see an F# project in the Solution Explorer.</span></span>

## <a name="writing-your-code"></a><span data-ttu-id="60e67-130">コードの記述</span><span class="sxs-lookup"><span data-stu-id="60e67-130">Writing your code</span></span>

<span data-ttu-id="60e67-131">最初にいくつかのコードを記述して開始しましょう。</span><span class="sxs-lookup"><span data-stu-id="60e67-131">Let's get started by writing some code first.</span></span>  <span data-ttu-id="60e67-132">確認して、`Program.fs`ファイルが開いている場合と、その内容を次に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="60e67-132">Make sure that the `Program.fs` file is open, and then replace its contents with the following:</span></span>

[!code-fsharp[HelloSquare](../../../samples/snippets/fsharp/getting-started/hello-square.fs)]

<span data-ttu-id="60e67-133">前のコード例の関数で`square`が定義されているという名前の入力を取り`x`単独で乗算します。</span><span class="sxs-lookup"><span data-stu-id="60e67-133">In the previous code sample, a function `square` has been defined which takes an input named `x` and multiplies it by itself.</span></span>  <span data-ttu-id="60e67-134">F# で使用されるため[型の推論](../language-reference/type-inference.md)の型`x`を指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="60e67-134">Because F# uses [Type Inference](../language-reference/type-inference.md), the type of `x` doesn't need to be specified.</span></span>  <span data-ttu-id="60e67-135">F# コンパイラは乗算が有効で型を認識し、型に割り当てられます`x`方法に基づいて`square`と呼びます。</span><span class="sxs-lookup"><span data-stu-id="60e67-135">The F# compiler understands the types where multiplication is valid, and will assign a type to `x` based on how `square` is called.</span></span>  <span data-ttu-id="60e67-136">ポインターを合わせる場合`square`次を参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="60e67-136">If you hover over `square`, you should see the following:</span></span>

```
val square: x:int -> int
```

<span data-ttu-id="60e67-137">これは、関数の型のシグネチャと呼ばれるものです。</span><span class="sxs-lookup"><span data-stu-id="60e67-137">This is what is known as the function's type signature.</span></span>  <span data-ttu-id="60e67-138">次のように読み取ることができます:"正方形をという名前の整数を受け取る関数は、x と整数が生成されます"です。</span><span class="sxs-lookup"><span data-stu-id="60e67-138">It can be read like this: "Square is a function which takes an integer named x and produces an integer".</span></span>  <span data-ttu-id="60e67-139">コンパイラから受け取った注`square`、`int`型ここでは、これは、ジェネリックであるため乗算いない間は*すべて*型しますが、ではなくがジェネリック型の closed set 間でします。</span><span class="sxs-lookup"><span data-stu-id="60e67-139">Note that the compiler gave `square` the `int` type for now - this is because multiplication is not generic across *all* types, but rather is generic across a closed set of types.</span></span>  <span data-ttu-id="60e67-140">選択、f# コンパイラ`int`このポイントが調整されます型シグネチャを呼び出す場合`square`と、別の入力など、型、`float`です。</span><span class="sxs-lookup"><span data-stu-id="60e67-140">The F# compiler picked `int` at this point, but it will adjust the type signature if you call `square` with a different input type, such as a `float`.</span></span>

<span data-ttu-id="60e67-141">別の関数、 `main`、定義されるで装飾されている、 `EntryPoint` f# コンパイラにそのプログラムの実行を指示する属性を開始する必要がありますがあります。</span><span class="sxs-lookup"><span data-stu-id="60e67-141">Another function, `main`, is defined, which is decorated with the `EntryPoint` attribute to tell the F# compiler that program execution should start there.</span></span>  <span data-ttu-id="60e67-142">その他のと同じ規則に従う[C スタイルのプログラミング言語](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B)コマンドライン引数は、この関数に渡すことが、整数コードが返されます (通常`0`)。</span><span class="sxs-lookup"><span data-stu-id="60e67-142">It follows the same convention as other [C-style programming languages](https://en.wikipedia.org/wiki/Entry_point#C_and_C.2B.2B), where command-line arguments can be passed to this function, and an integer code is returned (typically `0`).</span></span>

<span data-ttu-id="60e67-143">このために呼び出される関数では、`square`関数の引数を持つ`12`します。</span><span class="sxs-lookup"><span data-stu-id="60e67-143">It is in this function that we call the `square` function with an argument of `12`.</span></span>  <span data-ttu-id="60e67-144">F# コンパイラの型が割り当てられます`square`する`int -> int`(を受け取る関数は、`int`を生成し、 `int`)。</span><span class="sxs-lookup"><span data-stu-id="60e67-144">The F# compiler then assigns the type of `square` to be `int -> int` (that is, a function which takes an `int` and produces an `int`).</span></span>  <span data-ttu-id="60e67-145">呼び出し`printfn`を C スタイルのプログラミング言語、書式指定文字列で指定された値に対応するパラメーターに類似した形式の文字列を使用して書式設定された印刷機能であり、結果と新しい行に出力します。</span><span class="sxs-lookup"><span data-stu-id="60e67-145">The call to `printfn` is a formatted printing function which uses a format string, similar to C-style programming languages, parameters which correspond to those specified in the format string, and then prints the result and a new line.</span></span>

## <a name="running-your-code"></a><span data-ttu-id="60e67-146">コードの実行</span><span class="sxs-lookup"><span data-stu-id="60e67-146">Running your code</span></span>

<span data-ttu-id="60e67-147">コードを実行し をクリックして結果を表示することができます**実行**トップ レベル メニューからし**デバッグなしで開始**です。</span><span class="sxs-lookup"><span data-stu-id="60e67-147">You can run the code and see results by clicking on **Run** from the top level menu and then **Start Without Debugging**.</span></span>  <span data-ttu-id="60e67-148">これは、デバッグを行わず、プログラムを実行し、結果を確認することができます。</span><span class="sxs-lookup"><span data-stu-id="60e67-148">This will run the program without debugging and allows you to see the results.</span></span>

<span data-ttu-id="60e67-149">Visual Studio for Mac のポップをコンソール ウィンドウに出力され、次が表示されます。</span><span class="sxs-lookup"><span data-stu-id="60e67-149">You should now see the following printed to the console window that Visual Studio for Mac popped up:</span></span>

```
12 squared is 144!
```

<span data-ttu-id="60e67-150">おめでとうございます! </span><span class="sxs-lookup"><span data-stu-id="60e67-150">Congratulations!</span></span>  <span data-ttu-id="60e67-151">Mac 用 Visual Studio で初めての f# プロジェクトを作成、f# の関数は、その関数の呼び出しの結果を印刷書き込まれ、いくつかの結果を表示するプロジェクトを実行しました。</span><span class="sxs-lookup"><span data-stu-id="60e67-151">You've created your first F# project in Visual Studio for Mac, written an F# function printed the results of calling that function, and run the project to see some results.</span></span>

## <a name="using-f-interactive"></a><span data-ttu-id="60e67-152">F# Interactive を使用します。</span><span class="sxs-lookup"><span data-stu-id="60e67-152">Using F# Interactive</span></span>

<span data-ttu-id="60e67-153">最適な機能の Visual f# Mac のためのツールを Visual Studio での 1 つは、f# Interactive ウィンドウです。</span><span class="sxs-lookup"><span data-stu-id="60e67-153">One of the best features of the Visual F# tooling in Visual Studio for Mac is the F# Interactive Window.</span></span>  <span data-ttu-id="60e67-154">そのコードを呼び出すし、その結果を対話的に確認できますプロセスでコードを送信することができます。</span><span class="sxs-lookup"><span data-stu-id="60e67-154">It allows you to send code over to a process where you can call that code and see the result interactively.</span></span>

<span data-ttu-id="60e67-155">使用を開始するには、強調表示、`square`コードで定義された関数。</span><span class="sxs-lookup"><span data-stu-id="60e67-155">To begin using it, highlight the `square` function defined in your code.</span></span>  <span data-ttu-id="60e67-156">次に、をクリックして**編集**トップ レベル メニューからです。</span><span class="sxs-lookup"><span data-stu-id="60e67-156">Next, click on **Edit** from the top level menu.</span></span>  <span data-ttu-id="60e67-157">次に選択**選択範囲を f# Interactive に送信**です。</span><span class="sxs-lookup"><span data-stu-id="60e67-157">Next select **Send selection to F# Interactive**.</span></span>  <span data-ttu-id="60e67-158">これは、f# 対話型ウィンドウで、コードを実行します。</span><span class="sxs-lookup"><span data-stu-id="60e67-158">This executes the code in the F# Interactive Window.</span></span>  <span data-ttu-id="60e67-159">選択範囲を右クリックしを選択する代わりに、**選択範囲を f# Interactive に送信**です。</span><span class="sxs-lookup"><span data-stu-id="60e67-159">Alternatively, you can right click on the selection and choose **Send selection to F# Interactive**.</span></span>  <span data-ttu-id="60e67-160">F# 対話型ウィンドウ内に次の表示が表示されます。</span><span class="sxs-lookup"><span data-stu-id="60e67-160">You should see the F# Interactive Window appear with the following in it:</span></span>

```
>

val square : x:int -> int

>
```

<span data-ttu-id="60e67-161">同じ関数のシグネチャを示します、`square`関数で、先ほど見た関数に置かれているとします。</span><span class="sxs-lookup"><span data-stu-id="60e67-161">This shows the same function signature for the `square` function, which you saw earlier when you hovered over the function.</span></span>  <span data-ttu-id="60e67-162">`square`はこれで、f# Interactive のプロセスで定義されている、異なる値で呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="60e67-162">Because `square` is now defined in the F# Interactive process, you can call it with different values:</span></span>

```
> square 12;;
val it : int = 144
>square 13;;
val it : int = 169
```

<span data-ttu-id="60e67-163">これは、関数を実行、結果を新しい名前に束縛`it`の型および値を表示および`it`です。</span><span class="sxs-lookup"><span data-stu-id="60e67-163">This executes the function, binds the result to a new name `it`, and displays the type and value of `it`.</span></span>  <span data-ttu-id="60e67-164">各行を終了する必要がありますに注意してください`;;`です。</span><span class="sxs-lookup"><span data-stu-id="60e67-164">Note that you must terminate each line with `;;`.</span></span>  <span data-ttu-id="60e67-165">これは、どのように f# Interactive を知っている、関数呼び出しが完了するとします。</span><span class="sxs-lookup"><span data-stu-id="60e67-165">This is how F# Interactive knows when your function call is finished.</span></span>  <span data-ttu-id="60e67-166">F# Interactive で新しい関数を定義することもできます。</span><span class="sxs-lookup"><span data-stu-id="60e67-166">You can also define new functions in F# Interactive:</span></span>

```
> let isOdd x = x % 2 <> 0;;

val isOdd : x:int -> bool

> isOdd 12;;
val it : bool = false
```

<span data-ttu-id="60e67-167">上記の定義を新しい関数の場合、 `isOdd`、受け取り、`int`と奇数かどうかをチェック。</span><span class="sxs-lookup"><span data-stu-id="60e67-167">The above defines a new function, `isOdd`, which takes an `int` and checks to see if it's odd!</span></span>  <span data-ttu-id="60e67-168">異なる入力で返される内容を表示するには、この関数を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="60e67-168">You can call this function to see what it returns with different inputs.</span></span>  <span data-ttu-id="60e67-169">関数呼び出し内で関数を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="60e67-169">You can call functions within function calls:</span></span>

```
> isOdd (square 15);;
val it : bool = true
```

<span data-ttu-id="60e67-170">使用することも、[前方パイプ演算子](../language-reference/symbol-and-operator-reference/index.md)2 つの関数に値をパイプライン処理します。</span><span class="sxs-lookup"><span data-stu-id="60e67-170">You can also use the [pipe-forward operator](../language-reference/symbol-and-operator-reference/index.md) to pipeline the value into the two functions:</span></span>

```
> 15 |> square |> isOdd;;
val it : bool = true
```

<span data-ttu-id="60e67-171">後のチュートリアルでは、前方パイプ演算子などについて説明します。</span><span class="sxs-lookup"><span data-stu-id="60e67-171">The pipe-forward operator, and more, are covered in later tutorials.</span></span>

<span data-ttu-id="60e67-172">これは、f# Interactive で行うことができますに glimpse のみです。</span><span class="sxs-lookup"><span data-stu-id="60e67-172">This is only a glimpse into what you can do with F# Interactive.</span></span>  <span data-ttu-id="60e67-173">詳細については、チェック アウト[f# による対話型プログラミング](../tutorials/fsharp-interactive/index.md)です。</span><span class="sxs-lookup"><span data-stu-id="60e67-173">To learn more, check out [Interactive Programming with F#](../tutorials/fsharp-interactive/index.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="60e67-174">次のステップ</span><span class="sxs-lookup"><span data-stu-id="60e67-174">Next steps</span></span>

<span data-ttu-id="60e67-175">まだの場合はチェック アウト、[ツアーの f#](../tour.md)、f# 言語のコア機能の一部をカバーします。</span><span class="sxs-lookup"><span data-stu-id="60e67-175">If you haven't already, check out the [Tour of F#](../tour.md), which covers some of the core features of the F# language.</span></span>  <span data-ttu-id="60e67-176">一部の f# では、機能の概要を知るされ for Mac を Visual Studio にコピーし、実行できる十分なコード サンプルを入力します。</span><span class="sxs-lookup"><span data-stu-id="60e67-176">It will give you an overview of some of the capabilities of F#, and provide ample code samples that you can copy into Visual Studio for Mac and run.</span></span>  <span data-ttu-id="60e67-177">使用できますが、いくつかの優れた外部リソースからの[f# ガイド](../index.md)です。</span><span class="sxs-lookup"><span data-stu-id="60e67-177">There are also some great external resources you can use, showcased in the [F# Guide](../index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="60e67-178">関連項目</span><span class="sxs-lookup"><span data-stu-id="60e67-178">See also</span></span>
 [<span data-ttu-id="60e67-179">Visual F#</span><span class="sxs-lookup"><span data-stu-id="60e67-179">Visual F#</span></span>](../index.md)  
 [<span data-ttu-id="60e67-180">F# のツアー</span><span class="sxs-lookup"><span data-stu-id="60e67-180">Tour of F#</span></span>](../tour.md)  
 [<span data-ttu-id="60e67-181">F# 言語リファレンス</span><span class="sxs-lookup"><span data-stu-id="60e67-181">F# language reference</span></span>](../language-reference/index.md)  
 [<span data-ttu-id="60e67-182">型の推論</span><span class="sxs-lookup"><span data-stu-id="60e67-182">Type inference</span></span>](../language-reference/type-inference.md)  
 [<span data-ttu-id="60e67-183">シンボルと演算子のリファレンス</span><span class="sxs-lookup"><span data-stu-id="60e67-183">Symbol and operator reference</span></span>](../language-reference/symbol-and-operator-reference/index.md)  