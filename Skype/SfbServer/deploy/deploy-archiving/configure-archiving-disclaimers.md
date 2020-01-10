---
title: 針對商務用 Skype Server 中的外部使用者設定封存免責聲明
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 394ac291-05cd-4fa1-acb3-714af538b47f
description: 摘要：請閱讀本主題，以瞭解如何針對商務用 Skype Server 設定封存免責聲明。
ms.openlocfilehash: d6c08b6fe2eaa6c74231b96346661488c3f8e2b0
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001053"
---
# <a name="configure-archiving-disclaimers-for-external-users-in-skype-for-business-server"></a>針對商務用 Skype Server 中的外部使用者設定封存免責聲明
 
**摘要：** 若要瞭解如何針對商務用 Skype Server 設定封存免責聲明，請閱讀本主題。
  
如果您的組織與外部合作夥伴溝通，您必須讓他們知道您正在與他們封存通訊。 當您部署邊緣伺服器並為貴組織啟用同盟時，系統會詢問您是否要將封存免責聲明自動傳送給外部合作夥伴。 
  
如果您需要變更此設定，您可以使用商務用 Skype Server 的 [控制台] 或 [Windows PowerShell **CsAccessEdgeConfiguration** ] Cmdlet。 您可以從商務用 Skype Server management 命令介面或從 Windows PowerShell 遠端會話執行 Cmdlet。
  
若要讓外部使用者在商務用 Skype Server 部署中與使用者共同作業，您也必須至少設定一個外部存取原則以支援外部使用者存取。 如需詳細資訊，請參閱管理貴組織的 XMPP 聯盟合作夥伴。 如需控制特定聯盟網域存取權的詳細資料，請參閱依個別聯盟網域控制存取權。
  
## <a name="enable-or-disable-archiving-disclaimer-using-the-control-panel"></a>使用 [控制台] 啟用或停用封存放棄免責聲明

1. 從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或是指派給 CsAdministrator 角色，登入內部部署中的任何電腦。
    
2. 開啟瀏覽器視窗，然後輸入系統管理員 URL，開啟商務用 Skype Server 的 [控制台]。 
    
3. 在左側導覽列中，按一下 [**同盟與外部存取**]，然後按一下 [**存取邊緣**設定]。
    
4. 按一下 [**存取邊緣**設定] 索引標籤上的 [**全域**]，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。
    
5. 在 [**編輯存取邊緣**設定] 的 [**啟用同盟及公用 IM**連線] 底下，選取或清除 [**將封存放棄免責聲明傳送給聯盟夥伴**] 核取方塊，以啟用或停用自動傳送封存免責聲明。
    
6. 按一下 [認可]****。
    
## <a name="enable-or-disable-archiving-disclaimer-using-windows-powershell"></a>使用 Windows PowerShell 啟用或停用封存放棄免責聲明

若要啟用封存免責聲明，請將**EnableArchivingDisclaimer**屬性的值設定為 True （$True）：
  
```powershell
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True
```

若要停用封存免責聲明，請將**EnableArchivingDisclaimer**屬性的值設定為 False （$False）：
  
```powershell
Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False
```


