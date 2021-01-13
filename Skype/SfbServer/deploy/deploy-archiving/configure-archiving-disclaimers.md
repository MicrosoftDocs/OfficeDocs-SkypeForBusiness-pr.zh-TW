---
title: 在商務用 Skype Server 中設定外部使用者的封存免責聲明
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 394ac291-05cd-4fa1-acb3-714af538b47f
description: 摘要：閱讀此主題以瞭解如何為商務用 Skype 伺服器設定封存免責聲明。
ms.openlocfilehash: 055c94f0fba18dcd9de35ff5a73e37de0b45595b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820663"
---
# <a name="configure-archiving-disclaimers-for-external-users-in-skype-for-business-server"></a>在商務用 Skype Server 中設定外部使用者的封存免責聲明
 
**摘要：** 閱讀此主題以瞭解如何為商務用 Skype 伺服器設定封存免責聲明。
  
如果您的組織與外部合作夥伴進行通訊，您必須讓他們知道您正在封存與其通訊。 當您部署 Edge Server 並為您的組織啟用同盟時，系統會詢問您是否要自動將封存免責聲明傳送給外部合作夥伴。 
  
如果您需要變更此設定，您可以使用商務用 Skype Server 控制台或 Windows PowerShell **Set-CsAccessEdgeConfiguration** Cmdlet。 您可以從商務用 Skype Server 管理命令介面或從 Windows PowerShell 的遠端會話中執行 Cmdlet。
  
若要讓外部使用者能夠與商務用 Skype Server 部署中的使用者共同作業，您也必須至少設定一個外部存取原則，以支援外部使用者存取。 如需詳細資訊，請參閱管理組織的 XMPP 同盟合作夥伴。 如需控制特定同盟網域存取權的詳細資訊，請參閱控制個別同盟網域的存取。
  
## <a name="enable-or-disable-archiving-disclaimer-using-the-control-panel"></a>使用控制台啟用或停用封存免責聲明

1. 從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsAdministrator 角色，登入內部部署中的任何電腦。
    
2. 開啟瀏覽器視窗，然後輸入管理 URL 以開啟商務用 Skype Server 控制台。 
    
3. 在左導覽列中，按一下 [ **同盟和外部存取**]，然後按一下 [ **Access Edge** 設定]。
    
4. 在 [ **Access Edge** 設定] 索引標籤上，依序按一下 [ **全域**]、[ **編輯**] 和 [ **顯示詳細資料**]。
    
5. 在 [ **編輯 Access Edge** 設定] 的 [ **啟用同盟和公用 IM** 連線] 下，選取或清除 [將封存 **免責聲明傳送給同盟夥伴** ] 核取方塊，以啟用或停用自動傳送封存免責聲明。
    
6. 按一下 **[認可]**。
    
## <a name="enable-or-disable-archiving-disclaimer-using-windows-powershell"></a>使用 Windows PowerShell 啟用或停用封存免責聲明

若要啟用封存免責聲明，請將 **EnableArchivingDisclaimer** 屬性的值設為 True ($True) ：
  
```powershell
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True
```

若要停用封存免責聲明，請將 **EnableArchivingDisclaimer** 屬性的值設為 False ($False) ：
  
```powershell
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False
```


