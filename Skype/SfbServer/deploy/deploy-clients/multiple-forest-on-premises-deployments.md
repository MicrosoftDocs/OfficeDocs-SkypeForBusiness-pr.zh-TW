---
title: Skype會議室系統多個樹系內部部署
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6793fca0-3970-44e4-8703-1925428c1967
description: 閱讀此主題以瞭解如何在多樹系內部部署環境中部署 Skype 的會議室系統。
ms.openlocfilehash: 49885d1e64c40f161eb0fc07ec79187b5ea3bdb1
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60761581"
---
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a>Skype會議室系統多個樹系內部部署
 
閱讀此主題以瞭解如何在多樹系內部部署環境中部署 Skype 的會議室系統。
  
> [!NOTE]
> 為了在多個樹系中部署，Skype 的會議室系統需要在2013年8月 26 2014 日發行 Exchange Server CU6。 避免重複使用 Skype 房間系統的現有信箱。 使用新 (刪除舊的信箱，並重新建立) Skype 會議室系統的資源信箱。 若要還原因刪除信箱而遺失的會議，請參閱[連線或還原已刪除的信箱](/exchange/connect-or-restore-a-deleted-mailbox-exchange-2013-help)。 
  
在建立信箱之後，您可以使用 Set-CalendarProcessing 來設定信箱。 如需詳細資訊，請參閱單一樹系內部部署底下的步驟3到6。 在建立 Skype 會議室系統的 Exchange 資源信箱之後，請遵循在單一樹系內部部署上啟用商務用 Skype 的 Skype 會議室系統帳戶，以啟用商務用 Skype 的帳戶。
  
## <a name="option-1-create-a-new-resource-mailbox"></a>選項1：建立新的資源信箱

若要在多樹系環境中部署 Skype 的會議室系統：
  
1. 在 Active Directory (驗證樹系) 中建立連結的使用者 (LinkedRoomTest) 。
    
2. 在 Exchange Server 管理命令介面中執行下列命令：
    
   ```powershell
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a>選項2：將現有的會議室信箱變更為 Skype 的會議室系統 (連結) 資源信箱

```powershell
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
```