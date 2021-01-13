---
title: Skype 會議室系統多個樹系內部部署
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6793fca0-3970-44e4-8703-1925428c1967
description: 閱讀此主題以瞭解如何在多樹系內部部署環境中部署 Skype 會議室系統。
ms.openlocfilehash: 168244033a681b9aa9dc6e4c9697b7e3c7e89127
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805743"
---
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a><span data-ttu-id="9919b-103">Skype 會議室系統多個樹系內部部署</span><span class="sxs-lookup"><span data-stu-id="9919b-103">Skype Room System multiple forest on-premises deployments</span></span>
 
<span data-ttu-id="9919b-104">閱讀此主題以瞭解如何在多樹系內部部署環境中部署 Skype 會議室系統。</span><span class="sxs-lookup"><span data-stu-id="9919b-104">Read this topic to learn how to deploy Skype Room System in a multiple forest on-premises environment.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9919b-105">為了在多個樹系中部署，Skype 會議室系統需要 Exchange Server 2013 CU6 于年8月 26 2014 日發行。</span><span class="sxs-lookup"><span data-stu-id="9919b-105">In order to deploy in multiple forests, Skype Room System requires Exchange Server 2013 CU6 released on August 26, 2014.</span></span> <span data-ttu-id="9919b-106">避免重複使用 Skype 會議室系統的現有信箱。</span><span class="sxs-lookup"><span data-stu-id="9919b-106">Avoid re-using an existing mailbox for Skype Room System.</span></span> <span data-ttu-id="9919b-107">使用新 (刪除舊的信箱，並為 Skype 會議室系統重新建立) 資源信箱。</span><span class="sxs-lookup"><span data-stu-id="9919b-107">Use a new (delete old mailbox and re-create) resource mailbox for Skype Room System.</span></span> <span data-ttu-id="9919b-108">若要還原因刪除信箱而遺失的會議，請參閱連線 [或還原已刪除的信箱](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="9919b-108">To restore the meetings lost by deleting the mailbox, see [Connect or restore a deleted mailbox](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx).</span></span> 
  
<span data-ttu-id="9919b-109">在建立信箱之後，您可以使用 Set-CalendarProcessing 來設定信箱。</span><span class="sxs-lookup"><span data-stu-id="9919b-109">After creating the mailbox, you can use Set-CalendarProcessing to configure the mailbox.</span></span> <span data-ttu-id="9919b-110">如需詳細資訊，請參閱單一樹系內部部署底下的步驟3到6。</span><span class="sxs-lookup"><span data-stu-id="9919b-110">Refer to steps 3 through 6 under Single forest on-premises deployments for more details.</span></span> <span data-ttu-id="9919b-111">為商務用 skype 會議室建立 Exchange 資源信箱之後，請遵循在單一樹系內部部署中啟用商務用 skype 的 skype 會議室系統帳戶中的步驟，為商務用 Skype 啟用帳戶。</span><span class="sxs-lookup"><span data-stu-id="9919b-111">After creating an Exchange Resource mailbox for Skype Room System, enable the account for Skype for Business by following the steps in Enabling Skype Room System Accounts for Skype for Business under Single forest on-premises deployments.</span></span>
  
## <a name="option-1-create-a-new-resource-mailbox"></a><span data-ttu-id="9919b-112">選項1：建立新的資源信箱</span><span class="sxs-lookup"><span data-stu-id="9919b-112">Option 1: Create a new resource mailbox</span></span>

<span data-ttu-id="9919b-113">若要在多樹系環境中部署 Skype 會議室系統：</span><span class="sxs-lookup"><span data-stu-id="9919b-113">To deploy Skype Room System in a multi-forest environment:</span></span>
  
1. <span data-ttu-id="9919b-114">在 Active Directory (驗證樹系) 中建立連結的使用者 (LinkedRoomTest) 。</span><span class="sxs-lookup"><span data-stu-id="9919b-114">Create a Linked User (LinkedRoomTest) in Active Directory (Authentication Forest).</span></span>
    
2. <span data-ttu-id="9919b-115">在 Exchange Server 管理命令介面中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="9919b-115">Run the following commands in the Exchange Server Management Shell:</span></span>
    
   ```powershell
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a><span data-ttu-id="9919b-116">選項2：將現有的會議室信箱變更為 (連結) 資源信箱的 Skype 會議室系統</span><span class="sxs-lookup"><span data-stu-id="9919b-116">Option 2: Change an existing room mailbox to Skype Room System (linked) resource mailbox</span></span>

```powershell
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
```


