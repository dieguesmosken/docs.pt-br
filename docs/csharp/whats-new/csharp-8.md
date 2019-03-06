---
title: Novidades no C# 8.0 – Guia do C#
description: Obtenha uma visão geral dos novos recursos disponíveis no C# 8.0. Este artigo foi atualizado com a versão prévia 2.
ms.date: 02/12/2019
ms.openlocfilehash: 1aa5a200f84b35fda3c33a900655249d07000e8e
ms.sourcegitcommit: bd28ff1e312eaba9718c4f7ea272c2d4781a7cac
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/26/2019
ms.locfileid: "56835428"
---
# <a name="whats-new-in-c-80"></a><span data-ttu-id="9e993-104">Novidades no C# 8.0</span><span class="sxs-lookup"><span data-stu-id="9e993-104">What's new in C# 8.0</span></span>

<span data-ttu-id="9e993-105">Há vários aprimoramentos na linguagem C# que você já pode experimentar na versão prévia 2.</span><span class="sxs-lookup"><span data-stu-id="9e993-105">There are many enhancements to the C# language that you can try out already with preview 2.</span></span> <span data-ttu-id="9e993-106">Os novos recursos adicionados na versão prévia 2 são:</span><span class="sxs-lookup"><span data-stu-id="9e993-106">The new features added in preview 2 are:</span></span>

- <span data-ttu-id="9e993-107">[Aprimoramentos de correspondência de padrões](#more-patterns-in-more-places):</span><span class="sxs-lookup"><span data-stu-id="9e993-107">[Pattern matching enhancements](#more-patterns-in-more-places):</span></span>
  * [<span data-ttu-id="9e993-108">Expressões Switch</span><span class="sxs-lookup"><span data-stu-id="9e993-108">Switch expressions</span></span>](#switch-expressions)
  * [<span data-ttu-id="9e993-109">Padrões da propriedade</span><span class="sxs-lookup"><span data-stu-id="9e993-109">Property patterns</span></span>](#property-patterns)
  * [<span data-ttu-id="9e993-110">Padrões de tupla</span><span class="sxs-lookup"><span data-stu-id="9e993-110">Tuple patterns</span></span>](#tuple-patterns)
  * [<span data-ttu-id="9e993-111">Padrões posicionais</span><span class="sxs-lookup"><span data-stu-id="9e993-111">Positional patterns</span></span>](#positional-patterns)
- [<span data-ttu-id="9e993-112">Declarações using</span><span class="sxs-lookup"><span data-stu-id="9e993-112">Using declarations</span></span>](#using-declarations)
- [<span data-ttu-id="9e993-113">Funções locais estáticas</span><span class="sxs-lookup"><span data-stu-id="9e993-113">Static local functions</span></span>](#static-local-functions)
- [<span data-ttu-id="9e993-114">Estruturas ref descartáveis</span><span class="sxs-lookup"><span data-stu-id="9e993-114">Disposable ref structs</span></span>](#disposable-ref-structs)

<span data-ttu-id="9e993-115">Os recursos de linguagem a seguir apareceram pela primeira vez no C# 8.0 versão prévia 1:</span><span class="sxs-lookup"><span data-stu-id="9e993-115">The following language features first appeared in C# 8.0 preview 1:</span></span>

- [<span data-ttu-id="9e993-116">Tipos de referência nula</span><span class="sxs-lookup"><span data-stu-id="9e993-116">Nullable reference types</span></span>](#nullable-reference-types)
- [<span data-ttu-id="9e993-117">Fluxos assíncronos</span><span class="sxs-lookup"><span data-stu-id="9e993-117">Asynchronous streams</span></span>](#asynchronous-streams)
- [<span data-ttu-id="9e993-118">Índices e intervalos</span><span class="sxs-lookup"><span data-stu-id="9e993-118">Indices and ranges</span></span>](#indices-and-ranges)

> [!NOTE]
> <span data-ttu-id="9e993-119">Este artigo foi atualizado pela última vez para o C# 8.0 versão prévia 2.</span><span class="sxs-lookup"><span data-stu-id="9e993-119">This article was last updated for C# 8.0 preview 2.</span></span>

<span data-ttu-id="9e993-120">O restante deste artigo descreve rapidamente esses recursos.</span><span class="sxs-lookup"><span data-stu-id="9e993-120">The remainder of this article briefly describes these features.</span></span> <span data-ttu-id="9e993-121">Quando houver artigos detalhados disponíveis, forneceremos links para esses tutoriais e visões gerais.</span><span class="sxs-lookup"><span data-stu-id="9e993-121">Where in-depth articles are available, links to those tutorials and overviews are provided.</span></span>

## <a name="more-patterns-in-more-places"></a><span data-ttu-id="9e993-122">Mais padrões em mais partes</span><span class="sxs-lookup"><span data-stu-id="9e993-122">More patterns in more places</span></span>

<span data-ttu-id="9e993-123">Com a **correspondência de padrões**, você recebe ferramentas para fornecer funcionalidades dependentes da forma em tipos de dados relacionados, mas diferentes.</span><span class="sxs-lookup"><span data-stu-id="9e993-123">**Pattern matching** gives tools to provide shape-dependent functionality across related but different kinds of data.</span></span> <span data-ttu-id="9e993-124">O C# 7.0 introduziu uma sintaxe para padrões de tipo e padrões de constante usando a expressão [`is`](../language-reference/keywords/is.md) e a instrução [`switch`](../language-reference/keywords/switch.md).</span><span class="sxs-lookup"><span data-stu-id="9e993-124">C# 7.0 introduced syntax for type patterns and constant patterns by using the [`is`](../language-reference/keywords/is.md) expression and the [`switch`](../language-reference/keywords/switch.md) statement.</span></span> <span data-ttu-id="9e993-125">Esses recursos representaram os primeiros passos em direção ao suporte a paradigmas de programação, em que os dados e a funcionalidade vivem separados.</span><span class="sxs-lookup"><span data-stu-id="9e993-125">These features represented the first tentative steps toward supporting programming paradigms where data and functionality live apart.</span></span> <span data-ttu-id="9e993-126">À medida que o setor se aproxima mais de microsserviços e de outras arquiteturas baseadas em nuvem, outras ferramentas de linguagem de tornam necessárias.</span><span class="sxs-lookup"><span data-stu-id="9e993-126">As the industry moves toward more microservices and other cloud-based architectures, other language tools are needed.</span></span>

<span data-ttu-id="9e993-127">O C# 8.0 expande esse vocabulário, para que você possa usar mais expressões de padrão em mais partes do seu código.</span><span class="sxs-lookup"><span data-stu-id="9e993-127">C# 8.0 expands this vocabulary so you can use more pattern expressions in more places in your code.</span></span> <span data-ttu-id="9e993-128">Considere esses recursos quando seus dados e funcionalidades estiverem separados.</span><span class="sxs-lookup"><span data-stu-id="9e993-128">Consider these features when your data and functionality are separate.</span></span> <span data-ttu-id="9e993-129">Considere a correspondência de padrões quando seus algoritmos dependerem de um fato diferente do tipo de tempo de execução de um objeto.</span><span class="sxs-lookup"><span data-stu-id="9e993-129">Consider pattern matching when your algorithms depend on a fact other than the runtime type of an object.</span></span> <span data-ttu-id="9e993-130">Essas técnicas fornecem outra maneira de expressar designs.</span><span class="sxs-lookup"><span data-stu-id="9e993-130">These techniques provide another way to express designs.</span></span>

<span data-ttu-id="9e993-131">Além dos novos padrões em novas partes, o C# 8.0 adiciona **padrões recursivos**.</span><span class="sxs-lookup"><span data-stu-id="9e993-131">In addition to new patterns in new places, C# 8.0 adds **recursive patterns**.</span></span> <span data-ttu-id="9e993-132">O resultado de qualquer expressão padrão é uma expressão.</span><span class="sxs-lookup"><span data-stu-id="9e993-132">The result of any pattern expression is an expression.</span></span> <span data-ttu-id="9e993-133">Um padrão recursivo é simplesmente uma expressão padrão aplicada à saída de outra expressão padrão.</span><span class="sxs-lookup"><span data-stu-id="9e993-133">A recursive pattern is simply a pattern expression applied to the output of another pattern expression.</span></span>

### <a name="switch-expressions"></a><span data-ttu-id="9e993-134">Expressões switch</span><span class="sxs-lookup"><span data-stu-id="9e993-134">switch expressions</span></span>

<span data-ttu-id="9e993-135">Frequentemente, uma instrução [`switch`](../language-reference/keywords/switch.md) produz um valor em cada um de seus blocos `case`.</span><span class="sxs-lookup"><span data-stu-id="9e993-135">Often, a [`switch`](../language-reference/keywords/switch.md) statement produces a value in each of its `case` blocks.</span></span> <span data-ttu-id="9e993-136">As **expressões switch** permitem que você use a sintaxe de expressão mais concisa.</span><span class="sxs-lookup"><span data-stu-id="9e993-136">**Switch expressions** enable you to use more concise expression syntax.</span></span> <span data-ttu-id="9e993-137">Há menos palavras-chave `case` e `break` repetidas, e menos chaves.</span><span class="sxs-lookup"><span data-stu-id="9e993-137">There are fewer repetitive `case` and `break` keywords, and fewer curly braces.</span></span>  <span data-ttu-id="9e993-138">Por exemplo, considere a enumeração a seguir que lista as cores do arco-íris:</span><span class="sxs-lookup"><span data-stu-id="9e993-138">As an example, consider the following enum that lists the colors of the rainbow:</span></span>

```csharp
public enum Rainbow
{
    Red,
    Orange,
    Yellow,
    Blue,
    Indigo,
    Violet
}
```

<span data-ttu-id="9e993-139">Você poderia converter um valor `Rainbow` em valores RGB usando o seguinte método que contém uma expressão switch:</span><span class="sxs-lookup"><span data-stu-id="9e993-139">You could convert a `Rainbow` value to its RGB values using the following method containing a switch expression:</span></span>

```csharp
public static RGBColor FromRainbow(Rainbow colorBand) =>
    colorBand switch
    {
        Rainbow.Red    => new RGBColor(0xFF, 0x00, 0x00),
        Rainbow.Orange => new RGBColor(0xFF, 0x7F, 0x00),
        Rainbow.Yellow => new RGBColor(0xFF, 0xFF, 0x00),
        Rainbow.Blue   => new RGBColor(0x00, 0x00, 0xFF),
        Rainbow.Indigo => new RGBColor(0x4B, 0x00, 0x82),
        Rainbow.Violet => new RGBColor(0x94, 0x00, 0xD3),
        _              => throw new ArgumentException(message: "invalid enum value", paramName: nameof(colorBand)),
    };
```

<span data-ttu-id="9e993-140">Há vários aprimoramentos de sintaxe aqui:</span><span class="sxs-lookup"><span data-stu-id="9e993-140">There are several syntax improvements here:</span></span>

- <span data-ttu-id="9e993-141">A variável vem antes da palavra-chave `switch`.</span><span class="sxs-lookup"><span data-stu-id="9e993-141">The variable comes before the `switch` keyword.</span></span> <span data-ttu-id="9e993-142">A ordem diferente facilita distinguir visualmente a expressão switch da instrução switch.</span><span class="sxs-lookup"><span data-stu-id="9e993-142">The different order makes it visually easy to distinguish the switch expression from the switch statement.</span></span>
- <span data-ttu-id="9e993-143">Os elementos `case` e `:` são substituídos por `=>`.</span><span class="sxs-lookup"><span data-stu-id="9e993-143">The `case` and `:` elements are replaced with `=>`.</span></span> <span data-ttu-id="9e993-144">É mais conciso e intuitivo.</span><span class="sxs-lookup"><span data-stu-id="9e993-144">It's more concise and intuitive.</span></span>
- <span data-ttu-id="9e993-145">O caso `default` é substituído por um descarte `_`.</span><span class="sxs-lookup"><span data-stu-id="9e993-145">The `default` case is replaced with a `_` discard.</span></span>
- <span data-ttu-id="9e993-146">Os corpos são expressões, não instruções.</span><span class="sxs-lookup"><span data-stu-id="9e993-146">The bodies are expressions, not statements.</span></span>

<span data-ttu-id="9e993-147">Compare isso com o código equivalente usando a instrução clássica `switch`:</span><span class="sxs-lookup"><span data-stu-id="9e993-147">Contrast that with the equivalent code using the classic `switch` statement:</span></span>

```csharp
public static RGBColor fromRainbowClassic(Rainbow colorBand)
{
    switch (colorBand)
    {
        case Rainbow.Red:
            return new RGBColor(0xFF, 0x00, 0x00);
        case Rainbow.Orange:
            return new RGBColor(0xFF, 0x7F, 0x00);
        case Rainbow.Yellow:
            return new RGBColor(0xFF, 0xFF, 0x00);
        case Rainbow.Blue:
            return new RGBColor(0x00, 0x00, 0xFF);
        case Rainbow.Indigo:
            return new RGBColor(0x4B, 0x00, 0x82);
        case Rainbow.Violet:
            return new RGBColor(0x94, 0x00, 0xD3);
        default:
            throw new ArgumentException(message: "invalid enum value", paramName: nameof(colorBand));
    };
}
```

### <a name="property-patterns"></a><span data-ttu-id="9e993-148">Padrões da propriedade</span><span class="sxs-lookup"><span data-stu-id="9e993-148">Property patterns</span></span>

<span data-ttu-id="9e993-149">O **padrão da propriedade** permite que você compare as propriedades do objeto examinado.</span><span class="sxs-lookup"><span data-stu-id="9e993-149">The **property pattern** enables you to match on properties of the object examined.</span></span> <span data-ttu-id="9e993-150">Considere um site de comércio eletrônico que deve calcular o imposto da venda com base no endereço do comprador.</span><span class="sxs-lookup"><span data-stu-id="9e993-150">Consider an eCommerce site that must compute sales tax based on the buyer's address.</span></span> <span data-ttu-id="9e993-151">Esse cálculo não é uma responsabilidade principal de uma classe `Address`.</span><span class="sxs-lookup"><span data-stu-id="9e993-151">That computation is not a core responsibility of an `Address` class.</span></span> <span data-ttu-id="9e993-152">Ele mudará ao longo do tempo, provavelmente com mais frequência do que as alterações de formato de endereço.</span><span class="sxs-lookup"><span data-stu-id="9e993-152">It will change over time, likely more often than address format changes.</span></span> <span data-ttu-id="9e993-153">O valor do imposto depende da propriedade `State` do endereço.</span><span class="sxs-lookup"><span data-stu-id="9e993-153">The amount of sales tax depends on the `State` property of the address.</span></span> <span data-ttu-id="9e993-154">O método a seguir usa o padrão de propriedade para calcular o imposto da venda de acordo com o endereço e o preço:</span><span class="sxs-lookup"><span data-stu-id="9e993-154">The following method uses the property pattern to compute the sales tax from the address and the price:</span></span>

```csharp
public static decimal ComputeSalesTax(Address location, decimal salePrice) =>
    location switch
    {
        { State: "WA" } => salePrice * 0.06M,
        { State: "MN" } => salePrice * 0.75M,
        { State: "MI" } => salePrice * 0.05M,
        // other cases removed for brevity...
        _ => 0M
    };
```

<span data-ttu-id="9e993-155">A correspondência de padrão cria uma sintaxe concisa para expressar esse algoritmo.</span><span class="sxs-lookup"><span data-stu-id="9e993-155">Pattern matching creates a concise syntax for expressing this algorithm.</span></span>

### <a name="tuple-patterns"></a><span data-ttu-id="9e993-156">Padrões de tupla</span><span class="sxs-lookup"><span data-stu-id="9e993-156">Tuple patterns</span></span>

<span data-ttu-id="9e993-157">Alguns algoritmos dependem de várias entradas.</span><span class="sxs-lookup"><span data-stu-id="9e993-157">Some algorithms depend on multiple inputs.</span></span> <span data-ttu-id="9e993-158">**Padrões de tupla** permitem que você alterne com base em vários valores, expressadas como uma [tupla](../tuples.md).</span><span class="sxs-lookup"><span data-stu-id="9e993-158">**Tuple patterns** allow you to switch based on multiple values expressed as a [tuple](../tuples.md).</span></span>  <span data-ttu-id="9e993-159">O código a seguir mostra uma expressão de comutador para o jogo *pedra, papel, tesoura*:</span><span class="sxs-lookup"><span data-stu-id="9e993-159">The following code shows a switch expression for the game *rock, paper, scissors*:</span></span>

```csharp
public static string RockPaperScissors(string first, string second)
    => (first, second) switch
    {
        ("rock", "paper") => "rock is covered by paper. Paper wins.",
        ("rock", "scissors") => "rock breaks scissors. Rock wins.",
        ("paper", "rock") => "paper covers rock. Paper wins.",
        ("paper", "scissors") => "paper is cut by scissors. Scissors wins.",
        ("scissors", "rock") => "scissors is broken by rock. Rock wins.",
        ("scissors", "paper") => "scissors cuts paper. Scissors wins.",
        (_, _) => "tie"
    };
```

<span data-ttu-id="9e993-160">As mensagens indicam o vencedor.</span><span class="sxs-lookup"><span data-stu-id="9e993-160">The messages indicate the winner.</span></span> <span data-ttu-id="9e993-161">O caso de descarte representa três combinações para empates ou outras entradas de texto.</span><span class="sxs-lookup"><span data-stu-id="9e993-161">The discard case represents the three combinations for ties, or other text inputs.</span></span>

### <a name="positional-patterns"></a><span data-ttu-id="9e993-162">Padrões posicionais</span><span class="sxs-lookup"><span data-stu-id="9e993-162">Positional patterns</span></span>

<span data-ttu-id="9e993-163">Alguns tipos incluem um método `Deconstruct` que desconstrói suas propriedades em variáveis discretas.</span><span class="sxs-lookup"><span data-stu-id="9e993-163">Some types include a `Deconstruct` method that deconstructs its properties into discrete variables.</span></span> <span data-ttu-id="9e993-164">Quando um método `Deconstruct` é acessível, você pode usar **padrões posicionais** para inspecionar as propriedades do objeto e usar essas propriedades para um padrão.</span><span class="sxs-lookup"><span data-stu-id="9e993-164">When a `Deconstruct` method is accessible, you can use **positional patterns** to inspect properties of the object and use those properties for a pattern.</span></span>  <span data-ttu-id="9e993-165">Considere a seguinte classe `Point`, que inclui um método `Deconstruct` para criar variáveis discretas para `X` e `Y`:</span><span class="sxs-lookup"><span data-stu-id="9e993-165">Consider the following `Point` class that includes a `Deconstruct` method to create discrete variables for `X` and `Y`:</span></span>

```csharp
public class Point
{
    public int X { get; }
    public int Y { get; }

    public Point(int x, int y) => (X, Y) = (x, y);

    public void Deconstruct(out int x, out int y) =>
        (x, y) = (X, Y);
}
```

<span data-ttu-id="9e993-166">O método a seguir usa o **padrão posicional** para extrair os valores de `x` e `y`.</span><span class="sxs-lookup"><span data-stu-id="9e993-166">The following method uses the **positional pattern** to extract the values of `x` and `y`.</span></span> <span data-ttu-id="9e993-167">Em seguida, usa uma cláusula `when` para determinar o quadrante do ponto:</span><span class="sxs-lookup"><span data-stu-id="9e993-167">Then, it uses a `when` clause to determine the quadrant of the point:</span></span>

```csharp
static string Quadrant(Point p) => p switch
{
    (0, 0) => "origin",
    (var x, var y) when x > 0 && y > 0 => "Quadrant 1",
    (var x, var y) when x < 0 && y > 0 => "Quadrant 2",
    (var x, var y) when x < 0 && y < 0 => "Quadrant 3",
    (var x, var y) when x > 0 && y < 0 => "Quadrant 4",
    (var x, var y) => "on a border",
    _ => "unknown"
};
```

<span data-ttu-id="9e993-168">O padrão de descarte na switch anterior encontra a correspondência quando `x` ou `y`, mas não ambos, for 0.</span><span class="sxs-lookup"><span data-stu-id="9e993-168">The discard pattern in the preceding switch matches when either `x` or `y`, but not both, is 0.</span></span> <span data-ttu-id="9e993-169">Uma expressão switch deve produzir um valor ou lançar uma exceção.</span><span class="sxs-lookup"><span data-stu-id="9e993-169">A switch expression must either produce a value or throw an exception.</span></span> <span data-ttu-id="9e993-170">Se não houver correspondência em nenhum dos casos, a expressão switch gerará uma exceção.</span><span class="sxs-lookup"><span data-stu-id="9e993-170">If none of the cases match, the switch expression throws an exception.</span></span> <span data-ttu-id="9e993-171">O compilador gerará um aviso se você não cobrir todos os casos possíveis em sua expressão switch.</span><span class="sxs-lookup"><span data-stu-id="9e993-171">The compiler generates a warning for you if you do not cover all possible cases in your switch expression.</span></span>

## <a name="using-declarations"></a><span data-ttu-id="9e993-172">Declarações using</span><span class="sxs-lookup"><span data-stu-id="9e993-172">using declarations</span></span>

<span data-ttu-id="9e993-173">Uma **declaração using** é uma declaração de variável precedida pela palavra-chave `using`.</span><span class="sxs-lookup"><span data-stu-id="9e993-173">A **using declaration** is a variable declaration preceded by the `using` keyword.</span></span> <span data-ttu-id="9e993-174">Ele informa ao compilador que a variável que está sendo declarada deve ser descartada ao final do escopo delimitador.</span><span class="sxs-lookup"><span data-stu-id="9e993-174">It tells the compiler that the variable being declared should be disposed at the end of the enclosing scope.</span></span> <span data-ttu-id="9e993-175">Por exemplo, considere o seguinte código que grava um arquivo de texto:</span><span class="sxs-lookup"><span data-stu-id="9e993-175">For example, consider the following code that writes a text file:</span></span>

```csharp
static void WriteLinesToFile(IEnumerable<string> lines)
{
    using var file = new System.IO.StreamWriter("WriteLines2.txt");
    foreach (string line in lines)
    {
        // If the line doesn't contain the word 'Second', write the line to the file.
        if (!line.Contains("Second"))
        {
            file.WriteLine(line);
        }
    }
// file is disposed here
}
```

<span data-ttu-id="9e993-176">No exemplo anterior, o arquivo é descartado quando a chave de fechamento do método é atingida.</span><span class="sxs-lookup"><span data-stu-id="9e993-176">In the preceding example, the file is disposed when the closing brace for the method is reached.</span></span> <span data-ttu-id="9e993-177">Esse é o final do escopo no qual `file` é declarado.</span><span class="sxs-lookup"><span data-stu-id="9e993-177">That's the end of the scope in which `file` is declared.</span></span> <span data-ttu-id="9e993-178">O código anterior é equivalente ao código a seguir usando as [instruções using](../language-reference/keywords/using-statement.md) clássicas:</span><span class="sxs-lookup"><span data-stu-id="9e993-178">The preceding code is equivalent to the following code using the classic [using statements](../language-reference/keywords/using-statement.md) statement:</span></span>


```csharp
static void WriteLinesToFile(IEnumerable<string> lines)
{
    using (var file = new System.IO.StreamWriter("WriteLines2.txt"))
    {
        foreach (string line in lines)
        {
            // If the line doesn't contain the word 'Second', write the line to the file.
            if (!line.Contains("Second"))
            {
                file.WriteLine(line);
            }
        }
    } // file is disposed here
}
```

<span data-ttu-id="9e993-179">No exemplo anterior, o arquivo é descartado quando a chave de fechamento associada à instrução `using` é atingida.</span><span class="sxs-lookup"><span data-stu-id="9e993-179">In the preceding example, the file is disposed when the closing brace associated with the `using` statement is reached.</span></span>

<span data-ttu-id="9e993-180">Em ambos os casos, o compilador gera a chamada para `Dispose()`.</span><span class="sxs-lookup"><span data-stu-id="9e993-180">In both cases, the compiler generates the call to `Dispose()`.</span></span> <span data-ttu-id="9e993-181">O compilador gera um erro se a expressão na instrução using não for descartável.</span><span class="sxs-lookup"><span data-stu-id="9e993-181">The compiler generates an error if the expression in the using statement is not disposable.</span></span>

## <a name="static-local-functions"></a><span data-ttu-id="9e993-182">Funções locais estáticas</span><span class="sxs-lookup"><span data-stu-id="9e993-182">Static local functions</span></span>

<span data-ttu-id="9e993-183">Agora você pode adicionar o modificador `static` para funções locais a fim de garantir que essa função local não capture (faça referência) às variáveis no escopo delimitador.</span><span class="sxs-lookup"><span data-stu-id="9e993-183">You can now add the `static` modifier to local functions to ensure that local function doesn't capture (reference) any variables from the enclosing scope.</span></span> <span data-ttu-id="9e993-184">Isso gera `CS8421`, "Uma função local estática não pode conter uma referência a <variable>".</span><span class="sxs-lookup"><span data-stu-id="9e993-184">Doing so generates `CS8421`, "A static local function can't contain a reference to <variable>."</span></span> 

<span data-ttu-id="9e993-185">Considere o código a seguir.</span><span class="sxs-lookup"><span data-stu-id="9e993-185">Consider the following code.</span></span> <span data-ttu-id="9e993-186">A função local `LocalFunction` acessa a variável `y`, declarada no escopo delimitador (o método `M`).</span><span class="sxs-lookup"><span data-stu-id="9e993-186">The local function `LocalFunction` accesses the variable `y`, declared in the enclosing scope (the method `M`).</span></span> <span data-ttu-id="9e993-187">Portanto, `LocalFunction` não pode ser declarada com o modificador `static`:</span><span class="sxs-lookup"><span data-stu-id="9e993-187">Therefore, `LocalFunction` can't be declared with the `static` modifier:</span></span>

```csharp
int M()
{
    int y;
    LocalFunction();
    return y;

    void LocalFunction() => y = 0;
}
```

<span data-ttu-id="9e993-188">O código a seguir contém uma função local estática.</span><span class="sxs-lookup"><span data-stu-id="9e993-188">The following code contains a static local function.</span></span> <span data-ttu-id="9e993-189">Ela pode ser estática porque não acesse as variáveis no escopo delimitador:</span><span class="sxs-lookup"><span data-stu-id="9e993-189">It can be static because it doesn't access any variables in the enclosing scope:</span></span>

```csharp
int M()
{
    int y = 5;
    int x = 7;
    return Add(x, y);

    static int Add(int left, int right) => left + right;
}
```

## <a name="disposable-ref-structs"></a><span data-ttu-id="9e993-190">Estruturas ref descartáveis</span><span class="sxs-lookup"><span data-stu-id="9e993-190">Disposable ref structs</span></span>

<span data-ttu-id="9e993-191">Uma `struct` declarada com o modificador `ref` não pode implementar quaisquer interfaces e, portanto, não pode implementar <xref:System.IDisposable>.</span><span class="sxs-lookup"><span data-stu-id="9e993-191">A `struct` declared with the `ref` modifier may not implement any interfaces and so cannot implement <xref:System.IDisposable>.</span></span> <span data-ttu-id="9e993-192">Portanto, para permitir que uma `ref struct` seja descartada, ela deve ter um método `void Dispose()` acessível.</span><span class="sxs-lookup"><span data-stu-id="9e993-192">Therefore, to enable a `ref struct` to be disposed, it must have an accessible `void Dispose()` method.</span></span> <span data-ttu-id="9e993-193">Isso também se aplica às declarações `readonly ref struct`.</span><span class="sxs-lookup"><span data-stu-id="9e993-193">This also applies to `readonly ref struct` declarations.</span></span>

## <a name="nullable-reference-types"></a><span data-ttu-id="9e993-194">Tipos de referência anuláveis</span><span class="sxs-lookup"><span data-stu-id="9e993-194">Nullable reference types</span></span>

<span data-ttu-id="9e993-195">Dentro de um contexto de anotação anulável, qualquer variável de um tipo de referência é considerado um **tipo de referência não anulável**.</span><span class="sxs-lookup"><span data-stu-id="9e993-195">Inside a nullable annotation context, any variable of a reference type is considered to be a **nonnullable reference type**.</span></span> <span data-ttu-id="9e993-196">Se você quiser indicar que uma variável pode ser nula, acrescente o nome do tipo com o `?` para declarar a variável como um **tipo de referência anulável**.</span><span class="sxs-lookup"><span data-stu-id="9e993-196">If you want to indicate that a variable may be null, you must append the type name with the `?` to declare the variable as a **nullable reference type**.</span></span>

<span data-ttu-id="9e993-197">Para tipos de referência não anuláveis, o compilador usa a análise de fluxo para garantir que as variáveis locais sejam inicializadas como um valor não nulo quando declaradas.</span><span class="sxs-lookup"><span data-stu-id="9e993-197">For nonnullable reference types, the compiler uses flow analysis to ensure that local variables are initialized to a non-null value when declared.</span></span> <span data-ttu-id="9e993-198">Os campos devem ser inicializados durante a construção.</span><span class="sxs-lookup"><span data-stu-id="9e993-198">Fields must be initialized during construction.</span></span> <span data-ttu-id="9e993-199">O compilador gera um aviso se a variável não for definida por uma chamada para qualquer um dos construtores disponíveis ou por um inicializador.</span><span class="sxs-lookup"><span data-stu-id="9e993-199">The compiler generates a warning if the variable is not set by a call to any of the available constructors or by an initializer.</span></span> <span data-ttu-id="9e993-200">Além disso, os tipos de referência não anuláveis não podem receber um valor que possa ser nulo.</span><span class="sxs-lookup"><span data-stu-id="9e993-200">Furthermore, nonnullable reference types can't be assigned a value that could be null.</span></span>

<span data-ttu-id="9e993-201">Os tipos de referência anuláveis não são verificados para garantir que não tenham sido atribuídos ou inicializados como nulos.</span><span class="sxs-lookup"><span data-stu-id="9e993-201">Nullable reference types aren't checked to ensure they aren't assigned or initialized to null.</span></span> <span data-ttu-id="9e993-202">No entanto, o compilador usa a análise de fluxo para garantir que qualquer variável de um tipo de referência anulável passe por verificação com relação a um nulo antes de ser acessada ou atribuída a um tipo de referência não anulável.</span><span class="sxs-lookup"><span data-stu-id="9e993-202">However, the compiler uses flow analysis to ensure that any variable of a nullable reference type is checked against null before it's accessed or assigned to a nonnullable reference type.</span></span>

<span data-ttu-id="9e993-203">Saiba mais sobre o recurso na visão geral sobre [Tipos de referência anuláveis](../nullable-references.md).</span><span class="sxs-lookup"><span data-stu-id="9e993-203">You can learn more about the feature in the overview of [nullable reference types](../nullable-references.md).</span></span> <span data-ttu-id="9e993-204">Experimente-o em um novo aplicativo neste [tutorial de tipos de referência anuláveis](../tutorials/nullable-reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="9e993-204">Try it yourself in a new application in this [nullable reference types tutorial](../tutorials/nullable-reference-types.md).</span></span> <span data-ttu-id="9e993-205">Saiba mais sobre as etapas para migrar uma base de códigos existente para usar tipos de referência anuláveis no [tutorial sobre como migrar um aplicativo para usar tipos de referência anuláveis](../tutorials/upgrade-to-nullable-references.md).</span><span class="sxs-lookup"><span data-stu-id="9e993-205">Learn about the steps to migrate an existing codebase to make use of nullable reference types in the [migrating an application to use nullable reference types tutorial](../tutorials/upgrade-to-nullable-references.md).</span></span>

## <a name="asynchronous-streams"></a><span data-ttu-id="9e993-206">Fluxos assíncronos</span><span class="sxs-lookup"><span data-stu-id="9e993-206">Asynchronous streams</span></span>

<span data-ttu-id="9e993-207">A partir do C# 8.0, você pode criar e consumir fluxos de forma assíncrona.</span><span class="sxs-lookup"><span data-stu-id="9e993-207">Starting with C# 8.0, you can create and consume streams asynchronously.</span></span> <span data-ttu-id="9e993-208">Um método que retorna um fluxo assíncrono tem três propriedades:</span><span class="sxs-lookup"><span data-stu-id="9e993-208">A method that returns an asynchronous stream has three properties:</span></span>

1. <span data-ttu-id="9e993-209">Ele foi declarado com o modificador `async`.</span><span class="sxs-lookup"><span data-stu-id="9e993-209">It was declared with the `async` modifier.</span></span>
1. <span data-ttu-id="9e993-210">Ela retorna um <xref:System.Collections.Generic.IAsyncEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="9e993-210">It returns an <xref:System.Collections.Generic.IAsyncEnumerable%601>.</span></span>
1. <span data-ttu-id="9e993-211">O método contém instruções `yield return` para retornar elementos sucessivos no fluxo assíncrono.</span><span class="sxs-lookup"><span data-stu-id="9e993-211">The method contains `yield return` statements to return successive elements in the asynchronous stream.</span></span>

<span data-ttu-id="9e993-212">O consumo de um fluxo assíncrono exige que você adicione a palavra-chave `await` antes da palavra-chave `foreach` quando você enumera os elementos do fluxo.</span><span class="sxs-lookup"><span data-stu-id="9e993-212">Consuming an asynchronous stream requires you to add the `await` keyword before the `foreach` keyword when you enumerate the elements of the stream.</span></span> <span data-ttu-id="9e993-213">A adição da palavra-chave `await` exige o método que enumera o fluxo assíncrono seja declarado com o modificador `async` e retorne um tipo permitido para um método `async`.</span><span class="sxs-lookup"><span data-stu-id="9e993-213">Adding the `await` keyword requires the method that enumerates the asynchronous stream to be declared with the `async` modifier and to return a type allowed for an `async` method.</span></span> <span data-ttu-id="9e993-214">Normalmente, isso significa retornar um <xref:System.Threading.Tasks.Task> ou <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="9e993-214">Typically that means returning a <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="9e993-215">Também pode ser <xref:System.Threading.Tasks.ValueTask> ou <xref:System.Threading.Tasks.ValueTask%601>.</span><span class="sxs-lookup"><span data-stu-id="9e993-215">It can also be a <xref:System.Threading.Tasks.ValueTask> or <xref:System.Threading.Tasks.ValueTask%601>.</span></span> <span data-ttu-id="9e993-216">Um método pode consumir e produzir um fluxo assíncrono, o que significa que retornaria um <xref:System.Collections.Generic.IAsyncEnumerable%601>.</span><span class="sxs-lookup"><span data-stu-id="9e993-216">A method can both consume and produce an asynchronous stream, which means it would return an <xref:System.Collections.Generic.IAsyncEnumerable%601>.</span></span> <span data-ttu-id="9e993-217">O código a seguir gera uma sequência de 1 a 20, esperando 100 ms entre a geração de cada número:</span><span class="sxs-lookup"><span data-stu-id="9e993-217">The following code generates a sequence from 1 to 20, waiting 100 ms between generating each number:</span></span>

```csharp
public static async System.Collections.Generic.IAsyncEnumerable<int> GenerateSequence()
{
    for (int i = 0; i < 20; i++)
    {
        await Task.Delay(100);
        yield return i;
    }
}
```

<span data-ttu-id="9e993-218">Você enumeraria a sequência usando a instrução `await foreach`:</span><span class="sxs-lookup"><span data-stu-id="9e993-218">You would enumerate the sequence using the `await foreach` statement:</span></span>

```csharp
await foreach (var number in GenerateSequence())
{
    Console.WriteLine(number);
}
```

<span data-ttu-id="9e993-219">Experimente você mesmo os fluxos assíncronos em nosso tutorial sobre como [criar e consumir fluxos assíncronos](../tutorials/generate-consume-asynchronous-stream.md).</span><span class="sxs-lookup"><span data-stu-id="9e993-219">You can try asynchronous streams yourself in our tutorial on [creating and consuming async streams](../tutorials/generate-consume-asynchronous-stream.md).</span></span>

## <a name="indices-and-ranges"></a><span data-ttu-id="9e993-220">Índices e intervalos</span><span class="sxs-lookup"><span data-stu-id="9e993-220">Indices and ranges</span></span>

<span data-ttu-id="9e993-221">Intervalos e índices fornecem uma sintaxe sucinta para especificar subintervalos em uma matriz, <xref:System.Span%601> ou <xref:System.ReadOnlySpan%601>.</span><span class="sxs-lookup"><span data-stu-id="9e993-221">Ranges and indices provide a succinct syntax for specifying subranges in an array, <xref:System.Span%601>, or <xref:System.ReadOnlySpan%601>.</span></span>

<span data-ttu-id="9e993-222">Você pode especificar um índice **do final**.</span><span class="sxs-lookup"><span data-stu-id="9e993-222">You can specify an index **from the end**.</span></span> <span data-ttu-id="9e993-223">Especifique **do final** usando o operador `^`.</span><span class="sxs-lookup"><span data-stu-id="9e993-223">You specify **from the end** using the `^` operator.</span></span> <span data-ttu-id="9e993-224">Você está familiarizado com `array[2]` significando o elemento "2 desde o início".</span><span class="sxs-lookup"><span data-stu-id="9e993-224">You are familiar with `array[2]` meaning the element "2 from the start".</span></span> <span data-ttu-id="9e993-225">Agora, `array[^2]` significa o elemento "2 desde o final".</span><span class="sxs-lookup"><span data-stu-id="9e993-225">Now, `array[^2]` means the element "2 from the end".</span></span> <span data-ttu-id="9e993-226">O índice `^0` significa "final", ou o índice que segue o último elemento.</span><span class="sxs-lookup"><span data-stu-id="9e993-226">The index `^0` means "the end", or the index that follows the last element.</span></span>

<span data-ttu-id="9e993-227">Você pode especificar um **intervalo** com o **operador de intervalo**: `..`.</span><span class="sxs-lookup"><span data-stu-id="9e993-227">You can specify a **range** with the **range operator**: `..`.</span></span> <span data-ttu-id="9e993-228">Por exemplo, `0..^0` especifica todo o intervalo da matriz: 0 desde o início até, mas não incluindo, 0 do final.</span><span class="sxs-lookup"><span data-stu-id="9e993-228">For example, `0..^0` specifies the entire range of the array: 0 from the start up to, but not including 0 from the end.</span></span> <span data-ttu-id="9e993-229">Qualquer operando pode usar "desde o início" ou "desde o final".</span><span class="sxs-lookup"><span data-stu-id="9e993-229">Either operand may use "from the start" or "from the end".</span></span> <span data-ttu-id="9e993-230">Além disso, qualquer operando pode ser omitido.</span><span class="sxs-lookup"><span data-stu-id="9e993-230">Furthermore, either operand may be omitted.</span></span> <span data-ttu-id="9e993-231">Os padrões são `0` para o índice de início, e `^0` para o índice final.</span><span class="sxs-lookup"><span data-stu-id="9e993-231">The defaults are `0` for the start index, and `^0` for the end index.</span></span>

<span data-ttu-id="9e993-232">Vamos analisar alguns exemplos.</span><span class="sxs-lookup"><span data-stu-id="9e993-232">Let's look at a few examples.</span></span> <span data-ttu-id="9e993-233">Considere a matriz a seguir, anotada com seu índice do início e do final:</span><span class="sxs-lookup"><span data-stu-id="9e993-233">Consider the following array, annotated with its index from the start and from the end:</span></span>

```csharp
var words = new string[]
{
                // index from start    index from end
    "The",      // 0                   ^9
    "quick",    // 1                   ^8
    "brown",    // 2                   ^7
    "fox",      // 3                   ^6
    "jumped",   // 4                   ^5
    "over",     // 5                   ^4
    "the",      // 6                   ^3
    "lazy",     // 7                   ^2
    "dog"       // 8                   ^1
};
```

<span data-ttu-id="9e993-234">O índice de cada elemento reforça o conceito de "do início" e "do final", e que os intervalos excluem o fim do intervalo.</span><span class="sxs-lookup"><span data-stu-id="9e993-234">The index of each element reinforces the concept of "from the start", and "from the end", and that ranges are exclusive of the end of the range.</span></span> <span data-ttu-id="9e993-235">O "início" de toda a matriz é o primeiro elemento.</span><span class="sxs-lookup"><span data-stu-id="9e993-235">The "start" of the entire array is the first element.</span></span> <span data-ttu-id="9e993-236">O "final" de toda a matriz ocorre *após* o último elemento.</span><span class="sxs-lookup"><span data-stu-id="9e993-236">The "end" of the entire array is *past* the last element.</span></span>

<span data-ttu-id="9e993-237">Recupere a última palavra com o índice `^1`:</span><span class="sxs-lookup"><span data-stu-id="9e993-237">You can retrieve the last word with the `^1` index:</span></span>

```csharp
Console.WriteLine($"The last word is {words[^1]}");
// writes "dog"
```

<span data-ttu-id="9e993-238">O código a seguir cria um subintervalo com as palavras "quick", "brown" e "fox".</span><span class="sxs-lookup"><span data-stu-id="9e993-238">The following code creates a subrange with the words "quick", "brown", and "fox".</span></span> <span data-ttu-id="9e993-239">Ele inclui `words[1]` até `words[3]`.</span><span class="sxs-lookup"><span data-stu-id="9e993-239">It includes `words[1]` through `words[3]`.</span></span> <span data-ttu-id="9e993-240">O elemento `words[4]` não está no intervalo.</span><span class="sxs-lookup"><span data-stu-id="9e993-240">The element `words[4]` is not in the range.</span></span>

```csharp
var brownFox = words[1..4];
```

<span data-ttu-id="9e993-241">O código a seguir cria um subintervalo com "lazy" e "dog".</span><span class="sxs-lookup"><span data-stu-id="9e993-241">The following code creates a subrange with "lazy" and "dog".</span></span> <span data-ttu-id="9e993-242">Ele inclui `words[^2]` e `words[^1]`.</span><span class="sxs-lookup"><span data-stu-id="9e993-242">It includes `words[^2]` and `words[^1]`.</span></span> <span data-ttu-id="9e993-243">O índice final `words[^0]` não está incluído:</span><span class="sxs-lookup"><span data-stu-id="9e993-243">The end index `words[^0]` is not included:</span></span>

```csharp
var lazyDog = words[^2..^0];
```

<span data-ttu-id="9e993-244">Os exemplos a seguir criam intervalos abertos para o início, fim ou ambos:</span><span class="sxs-lookup"><span data-stu-id="9e993-244">The following examples create ranges that are open ended for the start, end, or both:</span></span>

```csharp
var allWords = words[..]; // contains "The" through "dog".
var firstPhrase = words[..4]; // contains "The" through "fox"
var lastPhrase = words[6..]; // contains "the, "lazy" and "dog"
```

<span data-ttu-id="9e993-245">Você também pode declarar intervalos como variáveis:</span><span class="sxs-lookup"><span data-stu-id="9e993-245">You can also declare ranges as variables:</span></span>

```csharp
Range phrase = 1..4;
```

<span data-ttu-id="9e993-246">Em seguida, o intervalo pode ser usado dentro dos caracteres `[` e `]`:</span><span class="sxs-lookup"><span data-stu-id="9e993-246">The range can then be used inside the `[` and `]` characters:</span></span>

```csharp
var text = words[phrase];
```