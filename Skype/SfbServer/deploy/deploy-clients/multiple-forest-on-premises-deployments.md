---
title: Skype 會議室系統多重林內部部署
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6793fca0-3970-44e4-8703-1925428c1967
description: 若要瞭解如何在多個目錄林內部部署環境中部署 Skype 會議室系統，請閱讀本主題。
ms.openlocfilehash: 13ff6b1dbf1c6ba0cf9c8effddaaae8f097de9ea
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003503"
---
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a>Skype 會議室系統多重林內部部署
 
若要瞭解如何在多個目錄林內部部署環境中部署 Skype 會議室系統，請閱讀本主題。
  
> [!NOTE]
> 若要在多個目錄林中進行部署，Skype 會議室系統需要在2014年8月26日發行 Exchange Server 2013 CU6。 避免重複使用 Skype 會議室系統的現有信箱。 針對 Skype 會議室系統，使用新的（刪除舊的信箱，然後重新建立）資源信箱。 若要透過刪除信箱來還原遺失的會議，請參閱[連接或還原已刪除的信箱](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx)。 
  
建立信箱之後，您可以使用 [設定] CalendarProcessing 來設定信箱。 如需詳細資訊，請參閱單一目錄林內部部署下的步驟3到6。 在為 Skype 會議室系統建立 Exchange 資源信箱之後，請按照在單一目錄林內部部署中啟用商務用 Skype 的 Skype 會議室系統帳戶中的步驟，來啟用商務用 Skype 的帳戶。
  
## <a name="option-1-create-a-new-resource-mailbox"></a>選項1：建立新的資源信箱

若要在多目錄林環境中部署 Skype 室系統：
  
1. 在 Active Directory （驗證林中）中建立連結的使用者（LinkedRoomTest）。
    
2. 在 Exchange Server 管理命令介面中執行下列命令：
    
   ```powershell
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a>選項2：將現有的會議室信箱變更為 Skype 會議室系統（連結）資源信箱

```powershell
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
```


