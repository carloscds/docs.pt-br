---
title: 'Como: Determinar os parâmetros com suporte em um codificador'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- encoder parameters [Windows Forms], determining supported
ms.assetid: f47ae459-e3ce-4d41-a140-2f6c6aea3f44
ms.openlocfilehash: 56b78a0cdfcb9ac8e3a7dbc12527fcc59f0524fd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54723401"
---
# <a name="how-to-determine-the-parameters-supported-by-an-encoder"></a>Como: Determinar os parâmetros com suporte em um codificador
Você pode ajustar os parâmetros de imagem, como o nível de qualidade e compactação, mas você deve saber quais parâmetros são suportados por um codificador de determinada imagem. O <xref:System.Drawing.Image> classe fornece o <xref:System.Drawing.Image.GetEncoderParameterList%2A> método para que você possa determinar quais parâmetros de imagem têm suporte para um codificador específico. Você pode especificar o codificador com um GUID. O <xref:System.Drawing.Image.GetEncoderParameterList%2A> método retorna uma matriz de <xref:System.Drawing.Imaging.EncoderParameter> objetos.  
  
## <a name="example"></a>Exemplo  
 O exemplo de código a seguir gera os parâmetros com suporte para o codificador JPEG. Use a lista de categorias de parâmetro e GUIDs associados no <xref:System.Drawing.Imaging.Encoder> visão geral da classe para determinar a categoria para cada parâmetro.  
  
 [!code-csharp[UsingImageEncodersDecoders#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#3)]
 [!code-vb[UsingImageEncodersDecoders#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#3)]  
  
## <a name="compiling-the-code"></a>Compilando o código  
 Este exemplo requer:  
  
-   Um aplicativo Windows Forms.  
  
-   Um <xref:System.Windows.Forms.PaintEventArgs>, que é um parâmetro de <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Consulte também
- [Como: Listar os codificadores instalados](../../../../docs/framework/winforms/advanced/how-to-list-installed-encoders.md)
- [Tipos de Bitmaps](../../../../docs/framework/winforms/advanced/types-of-bitmaps.md)
- [Usando Codificadores e Decodificadores de Imagem no GDI+ Gerenciado](../../../../docs/framework/winforms/advanced/using-image-encoders-and-decoders-in-managed-gdi.md)
