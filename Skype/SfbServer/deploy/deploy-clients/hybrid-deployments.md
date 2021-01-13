---
title: Skype 室系統混合式部署
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
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: 閱讀此主題以瞭解如何在混合式環境中部署 Skype 室系統。
ms.openlocfilehash: 47be9204155a1ff6cf6e8d9dfa67723a370fec26
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805893"
---
# <a name="skype-room-system-hybrid-deployments"></a><span data-ttu-id="56369-103">Skype 室系統混合式部署</span><span class="sxs-lookup"><span data-stu-id="56369-103">Skype Room System hybrid deployments</span></span>

<span data-ttu-id="56369-104">閱讀此主題以瞭解如何在混合式環境中部署 Skype 室系統。</span><span class="sxs-lookup"><span data-stu-id="56369-104">Read this topic to learn how to deploy Skype Room System in a hybrid environment.</span></span>
  
## <a name="hybrid-deployments"></a><span data-ttu-id="56369-105">混合式部署</span><span class="sxs-lookup"><span data-stu-id="56369-105">Hybrid deployments</span></span>

<span data-ttu-id="56369-106">如果您的拓撲具有商務用 Skype 伺服器和 Exchange Online，而且您想要在 Exchange Online 上裝載 Skype 會議室系統資源信箱，請遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="56369-106">Follow these steps if your topology has Skype for Business Server and Exchange Online, and you want to host the Skype Room System resource mailbox on Exchange Online.</span></span> <span data-ttu-id="56369-107">本節也涵蓋同時部署 Exchange Online 和 Exchange 伺服器的混合式案例。</span><span class="sxs-lookup"><span data-stu-id="56369-107">This section also covers a hybrid scenario where you have both Exchange Online and Exchange Server deployed.</span></span>
  
<span data-ttu-id="56369-108">出於說明目的，我們會針對線上網域使用內部部署網域和 LyncSample.ccstp.net 的 LyncSample.com。</span><span class="sxs-lookup"><span data-stu-id="56369-108">For illustrative purpose, we use LyncSample.com for the on-premises domain and LyncSample.ccstp.net for the online domain.</span></span>
  
1. <span data-ttu-id="56369-109">在 Exchange 系統管理中心中建立資源信箱 () LyncSample.ccsctp.net，方法是連線至 Exchange online 管理命令介面（如 Exchange Online 布建中所述）。</span><span class="sxs-lookup"><span data-stu-id="56369-109">Create a resource mailbox in Exchange admin center (LyncSample.ccsctp.net) by connecting to the Exchange Online Management shell as described in Exchange Online Provisioning.</span></span>
    
   ```powershell
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    <span data-ttu-id="56369-110">您可以使用 lrstest5@LyncSample.ccsctp.net 來驗證 OWA 連線性，以登入。</span><span class="sxs-lookup"><span data-stu-id="56369-110">You can verify OWA connectivity using lrstest5@LyncSample.ccsctp.net to log in.</span></span>
    
2. <span data-ttu-id="56369-111">在 Microsoft 365 或 Office 365 Exchange 系統管理中心中，新增電子郵件地址 lrstest5@LyncSample.com (部署網域) 並將其設為回復位址。</span><span class="sxs-lookup"><span data-stu-id="56369-111">In the Microsoft 365 or Office 365 Exchange admin center, add an e-mail address lrstest5@LyncSample.com (on-prem domain) and set it as the reply address.</span></span>
    
3. <span data-ttu-id="56369-112">建立部署 Active Directory 使用者 lrstest5@LyncSample.com，將電子郵件地址設定為 lrstest5@LyncSample.com，並將目標位址設定為 lrstest5@LyncSample.com。</span><span class="sxs-lookup"><span data-stu-id="56369-112">Create an on-prem Active Directory user lrstest5@LyncSample.com, set the e-mail address to lrstest5@LyncSample.com, and set the target address to lrstest5@LyncSample.com.</span></span>
    
4. <span data-ttu-id="56369-113">觸發目錄同步處理，而且在同步處理完成後，請確認使用者在 AAD 中合併，且您無法變更 Microsoft 365 或 Office 365 Exchange 系統管理中心中收件者資源的屬性。</span><span class="sxs-lookup"><span data-stu-id="56369-113">Trigger directory synchronization, and, after synchronization is complete, verify that users merge in AAD and that you are not able to change properties in recipient's resources in the Microsoft 365 or Office 365 Exchange admin center.</span></span>
    
5. <span data-ttu-id="56369-114">使用 lrstest5@LyncSample.com 驗證 OWA 連線。</span><span class="sxs-lookup"><span data-stu-id="56369-114">Verify OWA connectivity using lrstest5@LyncSample.com.</span></span> <span data-ttu-id="56369-115"> (早些時候，您已使用線上網域驗證 OWA 連線。 ) </span><span class="sxs-lookup"><span data-stu-id="56369-115">(Earlier, you verified OWA connectivity using the online domain.)</span></span>
    
    <span data-ttu-id="56369-116">在建立信箱之後，您可以在 Exchange Online 管理命令介面上使用 Set-CalendarProcessing 來設定信箱。</span><span class="sxs-lookup"><span data-stu-id="56369-116">After creating the mailbox, you can use Set-CalendarProcessing on the Exchange Online Management Shell to configure the mailbox.</span></span> <span data-ttu-id="56369-117">如需詳細資訊，請參閱部署部署的單一樹系中的步驟3到6。</span><span class="sxs-lookup"><span data-stu-id="56369-117">Refer to steps 3 through 6 under Single Forest On-prem Deployments for more details.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="56369-118">如果您有 Exchange Server 和 Exchange Online 的混合式環境，請移至 Exchange 管理命令介面，並 Enable-RemoteMailbox lrstest5@LyncSample.com-RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net。</span><span class="sxs-lookup"><span data-stu-id="56369-118">If you have a hybrid environment with Exchange Server and Exchange Online, go to the Exchange Management Shell and Enable-RemoteMailbox lrstest5@LyncSample.com -RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net -Room.</span></span> <span data-ttu-id="56369-119">然後觸發目錄同步處理。</span><span class="sxs-lookup"><span data-stu-id="56369-119">Then trigger Directory Synchronization.</span></span> 
  
    <span data-ttu-id="56369-120">如果您想要在 Exchange Online 中主控 Skype 室系統信箱，則不需要這些 Exchange 管理命令介面步驟，您可以繼續進行步驟6。</span><span class="sxs-lookup"><span data-stu-id="56369-120">If you want to host the Skype Room System mailbox in Exchange Online, these Exchange Management Shell steps are not required and you can proceed to step 6.</span></span>
    
6. <span data-ttu-id="56369-121">在商務用 Skype 管理命令介面上執行下列 Cmdlet，為商務用 skype 啟用商務用 skype 系統帳戶：</span><span class="sxs-lookup"><span data-stu-id="56369-121">Enable the Skype Room System account for Skype for Business by running the following cmdlet on Skype for Business Management Shell:</span></span>
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> <span data-ttu-id="56369-122">在上述案例中，如果您有商務用 Skype Online，而不是商務用 Skype Server，請在布建 Exchange 資源信箱之後，依照商務用 Skype Online 布妥中所述，布建商務用 skype 帳戶。</span><span class="sxs-lookup"><span data-stu-id="56369-122">If you have Skype for Business Online instead of Skype for Business Server in the above scenario, then after provisioning the Exchange resource mailbox, provision a Skype for Business account as described in Skype for Business Online Provisioning.</span></span> 
  

