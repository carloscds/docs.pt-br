---
title: Interface IHostTaskManager
ms.date: 03/30/2017
api_name:
- IHostTaskManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager
helpviewer_keywords:
- IHostTaskManager interface [.NET Framework hosting]
ms.assetid: 4a0b05b9-3ef1-4607-b7c8-bd4dd43647a0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3d7b85a30a5abd9186f039aa21cbe7790325e4f2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54545641"
---
# <a name="ihosttaskmanager-interface"></a>Interface IHostTaskManager
Fornece métodos que permitem que o common language runtime (CLR) para trabalhar com tarefas por meio do host em vez de usar as funções de threading ou fibra do sistema operacional padrão.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descrição|  
|------------|-----------------|  
|[Método BeginDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-begindelayabort-method.md)|Notifica o host que o código gerenciado está inserindo um período em que a tarefa atual não deve ser anulada.|  
|[Método BeginThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md)|Notifica o host que o código gerenciado está inserindo um período em que a tarefa atual não deve ser movida para outro thread do sistema operacional.|  
|[Método CallNeedsHostHook](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-callneedshosthook-method.md)|Permite que o host especificar se o common language runtime pode embutir a chamada especificada para uma função não gerenciada.|  
|[Método CreateTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-createtask-method.md)|Solicita que o host, crie uma nova tarefa.|  
|[Método EndDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enddelayabort-method.md)|Notifica o host que o código gerenciado está saindo do período em que a tarefa atual não deve ser interrompida, após uma chamada anterior para `BeginDelayAbort`.|  
|[Método EndThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md)|Notifica o host que o código gerenciado está saindo do período em que a tarefa atual não deve ser movida para outro thread do sistema operacional, seguindo uma chamada anterior para `BeginThreadAffinity`.|  
|[Método EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md)|Notifica o host que uma chamada para um método não gerenciado, como uma plataforma de invocação de método, está retornando o controle de execução para o CLR.|  
|[Método GetCurrentTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getcurrenttask-method.md)|Obtém um ponteiro de interface para a tarefa que está sendo executado no thread do sistema operacional do qual essa chamada é feita.|  
|[Método GetStackGuarantee](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getstackguarantee-method.md)|Obtém a quantidade de espaço de pilha é certamente estarão disponíveis após a conclusão de uma operação de pilha, mas antes do fechamento de um processo.|  
|[Método LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)|Notifica o host que o código gerenciado está prestes a fazer uma chamada para uma função não gerenciada.|  
|[Método ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md)|Notifica o host que está sendo feita uma chamada para o common language runtime (CLR) do código não gerenciado.|  
|[Método ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md)|Notifica o host que o controle está deixando o CLR e inserir uma função não gerenciada, por sua vez, chamado do código gerenciado.|  
|[Método SetCLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setclrtaskmanager-method.md)|Fornece o host com um ponteiro de interface para um [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md) instância implementada pelo CLR.|  
|[Método SetLocale](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setlocale-method.md)|Notifica o host que o CLR foi alterado a localidade da tarefa atual.|  
|[Método SetStackGuarantee](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setstackguarantee-method.md)|Reservado apenas para uso interno.|  
|[Método SetUILocale](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setuilocale-method.md)|Notifica o host que a localidade de interface do usuário foi alterada na tarefa atual.|  
|[Método Sleep](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md)|Notifica o host que a tarefa atual será suspenso.|  
|[Método SwitchToTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md)|Notifica o host que ele deve alternar a tarefa atual.|  
  
## <a name="remarks"></a>Comentários  
 `IHostTaskManager` permite que o CLR criar e gerenciar tarefas, para fornecer ganchos para o host para tomar uma ação quando o controle é transferido de gerenciado para código não gerenciado e vice-versa e para especificar determinadas ações o host pode e não pode tomar durante a execução de código.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Confira [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Cabeçalho:** MSCorEE.h  
  
 **Biblioteca:** Incluído como um recurso em mscoree. dll  
  
 **Versões do .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte também
- [Interface ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [Interface ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [Interface IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [Hospedagem de Interfaces](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
