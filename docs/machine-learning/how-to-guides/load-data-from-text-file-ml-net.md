---
title: Carregar dados de um arquivo de texto para o processamento do aprendizado de máquina – ML.NET
description: Descubra como carregar dados de um arquivo de texto para ser usado para criar, treinar e pontuar um modelo de aprendizado de máquina com o ML.NET
ms.date: 02/06/2019
ms.custom: mvc,how-to
ms.openlocfilehash: 70c7ccdeaa27b78a412c2bc82f524d4bf42a740a
ms.sourcegitcommit: d2ccb199ae6bc5787b4762e9ea6d3f6fe88677af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56091702"
---
# <a name="load-data-from-a-text-file-for-machine-learning-processing---mlnet"></a>Carregar dados de um arquivo de texto para o processamento do aprendizado de máquina – ML.NET

`TextLoader` é usado para carregar dados de arquivos de texto. Você precisa especificar as colunas de dados, seus tipos e sua localização no arquivo de texto.

Observe que é perfeitamente aceitável ler algumas colunas de um arquivo ou ler a mesma coluna várias vezes.

[Arquivo de exemplo](https://github.com/dotnet/machinelearning/blob/master/test/data/adult.tiny.with-schema.txt):

```console
Label   Workclass   education   marital-status
0   Private 11th    Never-married
0   Private HS-grad Married-civ-spouse
1   Local-gov   Assoc-acdm  Married-civ-spouse
1   Private Some-college    Married-civ-spouse
```

Para carregar os dados de um arquivo de texto:

```csharp
// Create a new context for ML.NET operations. It can be used for exception tracking and logging, 
// as a catalog of available operations and as the source of randomness.
var mlContext = new MLContext();

// Create the reader: define the data columns and where to find them in the text file.
var reader = mlContext.Data.CreateTextLoader(
    columns: new TextLoader.Column[]
    {
        // A boolean column depicting the 'target label'.
        new TextLoader.Column("IsOver50k",DataKind.BL,0),
        // Three text columns.
        new TextLoader.Column("WorkClass",DataKind.TX,1),
        new TextLoader.Column("Education",DataKind.TX,2),
        new TextLoader.Column("MaritalStatus",DataKind.TX,3)
    },
    hasHeader: true
);

// Now read the file (remember though, readers are lazy, so the actual reading will happen when the data is accessed).
var data = reader.Read(dataPath);
```