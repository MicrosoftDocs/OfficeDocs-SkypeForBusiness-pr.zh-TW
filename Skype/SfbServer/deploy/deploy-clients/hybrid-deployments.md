---
title: Skype 室系統混合式部署
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: 若要瞭解如何在混合式環境中部署 Skype 會議室系統, 請閱讀本主題。
ms.openlocfilehash: 37ed625ca97ba34a30ec6f4acbabce272ef6ac50
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192507"
---
# <a name="skype-room-system-hybrid-deployments"></a><span data-ttu-id="de95a-103">Skype 室系統混合式部署</span><span class="sxs-lookup"><span data-stu-id="de95a-103">Skype Room System hybrid deployments</span></span>

<span data-ttu-id="de95a-104">若要瞭解如何在混合式環境中部署 Skype 會議室系統, 請閱讀本主題。</span><span class="sxs-lookup"><span data-stu-id="de95a-104">Read this topic to learn how to deploy Skype Room System in a hybrid environment.</span></span>
  
## <a name="hybrid-deployments"></a><span data-ttu-id="de95a-105">混合式部署</span><span class="sxs-lookup"><span data-stu-id="de95a-105">Hybrid deployments</span></span>

<span data-ttu-id="de95a-106">如果您的拓撲具有商務用 Skype Server 和 Exchange Online, 且您想要在 Exchange Online 上裝載 Skype 會議室系統資源信箱, 請遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="de95a-106">Follow these steps if your topology has Skype for Business Server and Exchange Online, and you want to host the Skype Room System resource mailbox on Exchange Online.</span></span> <span data-ttu-id="de95a-107">本節也涵蓋您同時部署 Exchange Online 和 Exchange Server 的混合式案例。</span><span class="sxs-lookup"><span data-stu-id="de95a-107">This section also covers a hybrid scenario where you have both Exchange Online and Exchange Server deployed.</span></span>
  
<span data-ttu-id="de95a-108">針對說明用途, 我們將 LyncSample.com 用於內部部署網域, 並 LyncSample.ccstp.net online 網域。</span><span class="sxs-lookup"><span data-stu-id="de95a-108">For illustrative purpose, we use LyncSample.com for the on-premises domain and LyncSample.ccstp.net for the online domain.</span></span>
  
1. <span data-ttu-id="de95a-109">若要在 Exchange Online 管理命令介面 (LyncSample.ccsctp.net) 中建立資源信箱, 請參閱 Exchange Online 提供中的說明。</span><span class="sxs-lookup"><span data-stu-id="de95a-109">Create a resource mailbox in Exchange admin center (LyncSample.ccsctp.net) by connecting to the Exchange Online Management shell as described in Exchange Online Provisioning.</span></span>
    
   ```
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    <span data-ttu-id="de95a-110">您可以使用 lrstest5@LyncSample.ccsctp.net 驗證 OWA 連線性, 以登入。</span><span class="sxs-lookup"><span data-stu-id="de95a-110">You can verify OWA connectivity using lrstest5@LyncSample.ccsctp.net to log in.</span></span>
    
2. <span data-ttu-id="de95a-111">在 Office 365 Exchange 系統管理中心中, 新增電子郵件地址 lrstest5@LyncSample.com (在內部部署網域上), 並將其設定為回復位址。</span><span class="sxs-lookup"><span data-stu-id="de95a-111">In the Office 365 Exchange admin center, add an e-mail address lrstest5@LyncSample.com (on-prem domain) and set it as the reply address.</span></span>
    
3. <span data-ttu-id="de95a-112">建立內部部署 Active Directory 使用者 lrstest5@LyncSample.com、將電子郵件地址設定為 lrstest5@LyncSample.com, 然後將目標位址設定為 lrstest5@LyncSample.com。</span><span class="sxs-lookup"><span data-stu-id="de95a-112">Create an on-prem Active Directory user lrstest5@LyncSample.com, set the e-mail address to lrstest5@LyncSample.com, and set the target address to lrstest5@LyncSample.com.</span></span>
    
4. <span data-ttu-id="de95a-113">觸發目錄同步處理, 並在同步處理完成後, 確認使用者在 AAD 中進行合併, 且您無法在 Office365 Exchange 系統管理中心的收件者資源中變更屬性。</span><span class="sxs-lookup"><span data-stu-id="de95a-113">Trigger directory synchronization, and, after synchronization is complete, verify that users merge in AAD and that you are not able to change properties in recipient's resources in the Office365 Exchange admin center.</span></span>
    
5. <span data-ttu-id="de95a-114">使用 lrstest5@LyncSample.com 驗證 OWA 連線。</span><span class="sxs-lookup"><span data-stu-id="de95a-114">Verify OWA connectivity using lrstest5@LyncSample.com.</span></span> <span data-ttu-id="de95a-115">(較舊的版本), 您是使用線上網域驗證 OWA 連線性。)</span><span class="sxs-lookup"><span data-stu-id="de95a-115">(Earlier, you verified OWA connectivity using the online domain.)</span></span>
    
    <span data-ttu-id="de95a-116">建立信箱之後, 您可以在 Exchange Online 管理命令介面上使用 [CalendarProcessing] 來設定信箱。</span><span class="sxs-lookup"><span data-stu-id="de95a-116">After creating the mailbox, you can use Set-CalendarProcessing on the Exchange Online Management Shell to configure the mailbox.</span></span> <span data-ttu-id="de95a-117">如需詳細資訊, 請參閱單一目錄林內部部署部署底下的步驟3到6。</span><span class="sxs-lookup"><span data-stu-id="de95a-117">Refer to steps 3 through 6 under Single Forest On-prem Deployments for more details.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="de95a-118">如果您有混合式環境與 Exchange Server 和 Exchange Online, 請移至 Exchange 管理命令介面, 並啟用-RemoteMailbox lrstest5@LyncSample.com-RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net。</span><span class="sxs-lookup"><span data-stu-id="de95a-118">If you have a hybrid environment with Exchange Server and Exchange Online, go to the Exchange Management Shell and Enable-RemoteMailbox lrstest5@LyncSample.com -RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net -Room.</span></span> <span data-ttu-id="de95a-119">然後觸發目錄同步處理。</span><span class="sxs-lookup"><span data-stu-id="de95a-119">Then trigger Directory Synchronization.</span></span> 
  
    <span data-ttu-id="de95a-120">如果您想要在 Exchange Online 中裝載 Skype 會議室系統信箱, 則不需要這些 Exchange 管理命令介面步驟, 您可以繼續步驟6。</span><span class="sxs-lookup"><span data-stu-id="de95a-120">If you want to host the Skype Room System mailbox in Exchange Online, these Exchange Management Shell steps are not required and you can proceed to step 6.</span></span>
    
6. <span data-ttu-id="de95a-121">在商務用 Skype 管理命令介面上, 執行下列 Cmdlet 來啟用商務用 Skype 的 Skype 會議室系統帳戶:</span><span class="sxs-lookup"><span data-stu-id="de95a-121">Enable the Skype Room System account for Skype for Business by running the following cmdlet on Skype for Business Management Shell:</span></span>
    
   ```
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> <span data-ttu-id="de95a-122">如果您在上述案例中有商務用 Skype Online, 而不是商務用 Skype Server, 請在建立 Exchange 資源信箱之後, 按照商務用 Skype Online 設定中所述, 供應商務用 Skype 帳戶。</span><span class="sxs-lookup"><span data-stu-id="de95a-122">If you have Skype for Business Online instead of Skype for Business Server in the above scenario, then after provisioning the Exchange resource mailbox, provision a Skype for Business account as described in Skype for Business Online Provisioning.</span></span> 
  

