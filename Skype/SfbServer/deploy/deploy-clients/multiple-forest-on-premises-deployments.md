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
ms.openlocfilehash: eb5aa2cbe3bef26602279ffa9d4a5dc38a7e7bc2
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/06/2019
ms.locfileid: "36775038"
---
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a><span data-ttu-id="8e4ba-103">Skype 會議室系統多重林內部部署</span><span class="sxs-lookup"><span data-stu-id="8e4ba-103">Skype Room System multiple forest on-premises deployments</span></span>
 
<span data-ttu-id="8e4ba-104">若要瞭解如何在多個目錄林內部部署環境中部署 Skype 會議室系統，請閱讀本主題。</span><span class="sxs-lookup"><span data-stu-id="8e4ba-104">Read this topic to learn how to deploy Skype Room System in a multiple forest on-premises environment.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8e4ba-105">若要在多個目錄林中進行部署，Skype 會議室系統需要在2014年8月26日發行 Exchange Server 2013 CU6。</span><span class="sxs-lookup"><span data-stu-id="8e4ba-105">In order to deploy in multiple forests, Skype Room System requires Exchange Server 2013 CU6 released on August 26, 2014.</span></span> <span data-ttu-id="8e4ba-106">避免重複使用 Skype 會議室系統的現有信箱。</span><span class="sxs-lookup"><span data-stu-id="8e4ba-106">Avoid re-using an existing mailbox for Skype Room System.</span></span> <span data-ttu-id="8e4ba-107">針對 Skype 會議室系統，使用新的（刪除舊的信箱，然後重新建立）資源信箱。</span><span class="sxs-lookup"><span data-stu-id="8e4ba-107">Use a new (delete old mailbox and re-create) resource mailbox for Skype Room System.</span></span> <span data-ttu-id="8e4ba-108">若要透過刪除信箱來還原遺失的會議，請參閱[連接或還原已刪除的信箱](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="8e4ba-108">To restore the meetings lost by deleting the mailbox, see [Connect or restore a deleted mailbox](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx).</span></span> 
  
<span data-ttu-id="8e4ba-109">建立信箱之後，您可以使用 [設定] CalendarProcessing 來設定信箱。</span><span class="sxs-lookup"><span data-stu-id="8e4ba-109">After creating the mailbox, you can use Set-CalendarProcessing to configure the mailbox.</span></span> <span data-ttu-id="8e4ba-110">如需詳細資訊，請參閱單一目錄林內部部署下的步驟3到6。</span><span class="sxs-lookup"><span data-stu-id="8e4ba-110">Refer to steps 3 through 6 under Single forest on-premises deployments for more details.</span></span> <span data-ttu-id="8e4ba-111">在為 Skype 會議室系統建立 Exchange 資源信箱之後，請按照在單一目錄林內部部署中啟用商務用 Skype 的 Skype 會議室系統帳戶中的步驟，來啟用商務用 Skype 的帳戶。</span><span class="sxs-lookup"><span data-stu-id="8e4ba-111">After creating an Exchange Resource mailbox for Skype Room System, enable the account for Skype for Business by following the steps in Enabling Skype Room System Accounts for Skype for Business under Single forest on-premises deployments.</span></span>
  
## <a name="option-1-create-a-new-resource-mailbox"></a><span data-ttu-id="8e4ba-112">選項1：建立新的資源信箱</span><span class="sxs-lookup"><span data-stu-id="8e4ba-112">Option 1: Create a new resource mailbox</span></span>

<span data-ttu-id="8e4ba-113">若要在多目錄林環境中部署 Skype 室系統：</span><span class="sxs-lookup"><span data-stu-id="8e4ba-113">To deploy Skype Room System in a multi-forest environment:</span></span>
  
1. <span data-ttu-id="8e4ba-114">在 Active Directory （驗證林中）中建立連結的使用者（LinkedRoomTest）。</span><span class="sxs-lookup"><span data-stu-id="8e4ba-114">Create a Linked User (LinkedRoomTest) in Active Directory (Authentication Forest).</span></span>
    
2. <span data-ttu-id="8e4ba-115">在 Exchange Server 管理命令介面中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="8e4ba-115">Run the following commands in the Exchange Server Management Shell:</span></span>
    
   ```
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a><span data-ttu-id="8e4ba-116">選項2：將現有的會議室信箱變更為 Skype 會議室系統（連結）資源信箱</span><span class="sxs-lookup"><span data-stu-id="8e4ba-116">Option 2: Change an existing room mailbox to Skype Room System (linked) resource mailbox</span></span>

```
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
```


