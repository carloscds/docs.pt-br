---
title: 'Como: Trabalhos de impressão de formulários do Windows completa'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print jobs [Windows Forms], completing in Windows Forms
- printing [Windows Forms], print jobs
ms.assetid: 23ec74f7-34c5-4710-82a0-ee2914518548
ms.openlocfilehash: f7504d645ea1fca6f45b17f79eb576919b782263
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54572819"
---
# <a name="how-to-complete-windows-forms-print-jobs"></a>Como: Trabalhos de impressão de formulários do Windows completa
Frequentemente, processadores de texto e outros aplicativos que envolvem impressão fornecerão a opção para exibir uma mensagem aos usuários de que um trabalho de impressão foi concluído. Você pode fornecer essa funcionalidade em seus formulários do Windows manipulando o <xref:System.Drawing.Printing.PrintDocument.EndPrint> eventos do <xref:System.Drawing.Printing.PrintDocument> componente.  
  
 O procedimento a seguir requer que você tenha criado um aplicativo baseado em Windows com um <xref:System.Drawing.Printing.PrintDocument> componente nele, que é a maneira padrão de habilitar a impressão de um aplicativo baseado em Windows. Para obter mais informações sobre impressão nos Windows Forms usando o <xref:System.Drawing.Printing.PrintDocument> componente, consulte [como: Criar trabalhos de impressão padrão do Windows Forms](../../../../docs/framework/winforms/advanced/how-to-create-standard-windows-forms-print-jobs.md).  
  
### <a name="to-complete-a-print-job"></a>Para concluir um trabalho de impressão  
  
1.  Defina as <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> propriedade do <xref:System.Drawing.Printing.PrintDocument> componente.  
  
    ```vb  
    PrintDocument1.DocumentName = "MyTextFile"  
    ```  
  
    ```csharp  
    printDocument1.DocumentName = "MyTextFile";  
    ```  
  
    ```cpp  
    printDocument1->DocumentName = "MyTextFile";  
    ```  
  
2.  Escrever código para manipular o <xref:System.Drawing.Printing.PrintDocument.EndPrint> eventos.  
  
     No exemplo de código a seguir, uma caixa de mensagem é exibida, indicando que o documento terminou a impressão.  
  
    ```vb  
    Private Sub PrintDocument1_EndPrint(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintEventArgs) Handles PrintDocument1.EndPrint  
       MessageBox.Show(PrintDocument1.DocumentName + " has finished printing.")  
    End Sub  
    ```  
  
    ```csharp  
    private void printDocument1_EndPrint(object sender,   
    System.Drawing.Printing.PrintEventArgs e)  
    {  
       MessageBox.Show(printDocument1.DocumentName +   
          " has finished printing.");  
    }  
    ```  
  
    ```cpp  
    private:  
       void printDocument1_EndPrint(System::Object ^ sender,  
          System::Drawing::Printing::PrintEventArgs ^ e)  
       {  
          MessageBox::Show(String::Concat(printDocument1->DocumentName,  
             " has finished printing."));  
       }  
    ```  
  
     (Visual c# e [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) coloque o seguinte código no construtor do formulário para registrar o manipulador de eventos.  
  
    ```csharp  
    this.printDocument1.EndPrint += new  
       System.Drawing.Printing.PrintEventHandler  
       (this.printDocument1_EndPrint);  
    ```  
  
    ```cpp  
    this->printDocument1->EndPrint += gcnew  
       System::Drawing::Printing::PrintEventHandler  
       (this, &Form1::printDocument1_EndPrint);  
    ```  
  
## <a name="see-also"></a>Consulte também
- <xref:System.Drawing.Printing.PrintDocument>
- [Suporte à impressão nos Windows Forms](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)
