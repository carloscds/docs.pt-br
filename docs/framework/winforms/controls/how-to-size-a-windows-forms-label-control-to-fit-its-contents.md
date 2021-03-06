---
title: 'Como: Dimensionar um controle de rótulo do Windows Forms para ajustar seu conteúdo'
ms.date: 03/30/2017
helpviewer_keywords:
- captions [Windows Forms], sizing
- sizing controls
- size [Windows Forms], controls
- labels [Windows Forms], sizing to fit contents
- Label control [Windows Forms], sizing to fit contents
ms.assetid: 99648964-63b2-438c-980e-d24103ad602b
ms.openlocfilehash: 74947e529a472c9e9a681fcb436ce8aff990c0af
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54640388"
---
# <a name="how-to-size-a-windows-forms-label-control-to-fit-its-contents"></a>Como: Dimensionar um controle de rótulo do Windows Forms para ajustar seu conteúdo
Os formulários do Windows <xref:System.Windows.Forms.Label> controle pode ser uma linha ou várias linhas, e podem ser fixas de tamanho ou pode redimensionar automaticamente para acomodar sua legenda. O <xref:System.Windows.Forms.Label.AutoSize%2A> propriedade ajuda você a dimensionar os controles para ajustar as legendas de maiores ou menores, que é particularmente útil se a legenda será alterado em tempo de execução.  
  
### <a name="to-make-a-label-control-resize-dynamically-to-fit-its-contents"></a>Para fazer com que um controle de rótulo redimensionar dinamicamente para ajustar seu conteúdo  
  
1.  Defina suas <xref:System.Windows.Forms.Label.AutoSize%2A> propriedade para `true`.  
  
 Se <xref:System.Windows.Forms.Label.AutoSize%2A> é definido como `false`, palavras especificadas no <xref:System.Windows.Forms.Label.Text%2A> propriedade será encapsulado para a próxima linha se possível, mas o controle não crescerá.  
  
## <a name="see-also"></a>Consulte também
- [Como: Criar chaves de acesso com controles de rótulo dos Windows Forms](../../../../docs/framework/winforms/controls/how-to-create-access-keys-with-windows-forms-label-controls.md)
- [Visão geral do controle Label](../../../../docs/framework/winforms/controls/label-control-overview-windows-forms.md)
- [Controle de rótulo](../../../../docs/framework/winforms/controls/label-control-windows-forms.md)
