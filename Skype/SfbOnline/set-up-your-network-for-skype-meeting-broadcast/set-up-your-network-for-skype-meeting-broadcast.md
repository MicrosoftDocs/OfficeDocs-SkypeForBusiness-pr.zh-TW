---
title: 為您的 Skype 會議廣播設定網路
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.topic: article
ms.assetid: dfa736b9-4920-4f48-b8c0-b5487ec6086f
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- SMB
description: 瞭解商務用 Skype Online 的 Skype 會議廣播功能，此功能可讓您排程、製作會議和廣播會議或活動給最多 10，000 名出席者的大型線上觀眾。
ms.openlocfilehash: 513b6f8d677550557293855389eff29dc61c21c1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51106509"
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a><span data-ttu-id="b7fe1-103">為您的 Skype 會議廣播設定網路</span><span class="sxs-lookup"><span data-stu-id="b7fe1-103">Set up your network for Skype Meeting Broadcast</span></span>

<span data-ttu-id="b7fe1-104">啟用 Skype [會議廣播 Skype](enable-skype-meeting-broadcast.md) 會議廣播之後，您需要設定您的網路。</span><span class="sxs-lookup"><span data-stu-id="b7fe1-104">After you [Enable Skype Meeting Broadcast](enable-skype-meeting-broadcast.md) Skype Meeting Broadcast, you need to configure your network.</span></span> <span data-ttu-id="b7fe1-105">如果您想要為公司外部人員舉辦網路研討會和其他廣播，請執行此步驟。</span><span class="sxs-lookup"><span data-stu-id="b7fe1-105">Do this step if you want to hold webinars and other broadcasts for people outside of your business.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b7fe1-106">商務用 Skype Online 將于 2021 年 7 月 31 日停用，此時將結束服務存取權。</span><span class="sxs-lookup"><span data-stu-id="b7fe1-106">Skype for Business Online is retiring on July 31, 2021, at which time access to the service will end.</span></span> <span data-ttu-id="b7fe1-107">我們鼓勵客戶開始升級至 Microsoft 365 中通訊和團隊合作的核心用戶端 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="b7fe1-107">We encourage customers to begin the upgrade to Microsoft Teams, the core client for communications and teamwork in Microsoft 365.</span></span>

<span data-ttu-id="b7fe1-108">如果您沒有防火牆的組組經驗，請考慮雇用 [Microsoft 合作夥伴](https://go.microsoft.com/fwlink/?linkid=391089) 來執行此步驟。</span><span class="sxs-lookup"><span data-stu-id="b7fe1-108">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>

<span data-ttu-id="b7fe1-109">若要略過此步驟，改為將另一個企業新增到您的聯盟，以便邀請他們參加廣播，請遵循允許使用者與外部 [商務用 Skype 使用者](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)聯繫中的步驟。</span><span class="sxs-lookup"><span data-stu-id="b7fe1-109">To skip this step and instead add another business to your federation so you can invite them to broadcasts, follow the steps in [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span>

## <a name="step-1-set-up-allowed-domains"></a><span data-ttu-id="b7fe1-110">步驟 1：設定允許的網域</span><span class="sxs-lookup"><span data-stu-id="b7fe1-110">Step 1: Set up allowed domains</span></span>

<span data-ttu-id="b7fe1-111">使用 **下列** 其中一種方法來設定允許的網域：</span><span class="sxs-lookup"><span data-stu-id="b7fe1-111">Use **one** of the following methods to set up allowed domains:</span></span>

## #

 <span data-ttu-id="b7fe1-112">**方法 1：使用系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="b7fe1-112">**Method 1: Use the admin center**</span></span>

1. <span data-ttu-id="b7fe1-113">請前往系統管理中心，然後在左側導航區中，按一下[設定服務附加元件，  >  **&amp;** 然後選擇 **商務用 Skype。**</span><span class="sxs-lookup"><span data-stu-id="b7fe1-113">Go to the admin center and then in the left nav, click **Settings** > **Services &amp; add-ins**, and then choose **Skype for Business**.</span></span>

2. <span data-ttu-id="b7fe1-114">在外部 **共用\*\*\*\*頁面上的網** 域例外情形下，選取 所有網域都封鎖，然後輸入下列網域，以逗號分隔 (，) ：</span><span class="sxs-lookup"><span data-stu-id="b7fe1-114">On the **External sharing** page under **Domain exceptions**, select **All domains are blocked except**, and enter the following domains, separated with a comma (,):</span></span>

   - <span data-ttu-id="b7fe1-115">noammeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="b7fe1-115">noammeetings.lync.com</span></span>

   - <span data-ttu-id="b7fe1-116">emeameetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="b7fe1-116">emeameetings.lync.com</span></span>

   - <span data-ttu-id="b7fe1-117">apacmeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="b7fe1-117">apacmeetings.lync.com</span></span>

   - <span data-ttu-id="b7fe1-118">resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="b7fe1-118">resources.lync.com</span></span>

3. <span data-ttu-id="b7fe1-119">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="b7fe1-119">Click **Save**.</span></span>

## #

 <span data-ttu-id="b7fe1-120">**方法 2：使用 Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="b7fe1-120">**Method 2: Use Windows PowerShell**</span></span>

- <span data-ttu-id="b7fe1-121">從 [ **開始功能表上**，以滑鼠右鍵 **按一下 Windows PowerShell，** 然後按一下 **[以系統管理員的執行**> 。</span><span class="sxs-lookup"><span data-stu-id="b7fe1-121">From the **Start Menu**, right-click **Windows PowerShell** and click **Run as administrator**.</span></span> <span data-ttu-id="b7fe1-122">在 **Windows PowerShell 視窗中** ，輸入每一行，然後按 Enter。</span><span class="sxs-lookup"><span data-stu-id="b7fe1-122">In the **Windows PowerShell** window, type each line and press Enter.</span></span>

  ```PowerShell
  $r = New-CsEdgeDomainPattern -Domain "noammeetings.lync.com"
  ```

  ```PowerShell
  $s = New-CsEdgeDomainPattern -Domain "emeameetings.lync.com"
  ```

  ```PowerShell
  $t = New-CsEdgeDomainPattern -Domain "apacmeetings.lync.com"
  ```

  ```PowerShell
  $n = New-CsEdgeDomainPattern -Domain "resources.lync.com"
  ```

  ```PowerShell
  $newAllowList = New-CsEdgeAllowList -AllowedDomain $r,$s,$t,$n
  ```

  ```PowerShell
  Set-CsTenantFederationConfiguration -AllowedDomains $newAllowList
  ```

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a><span data-ttu-id="b7fe1-123">步驟 2：新增 Skype 會議廣播網域、URL 和 IP 位址</span><span class="sxs-lookup"><span data-stu-id="b7fe1-123">Step 2: Add Skype Meeting Broadcast domains, URLs, and IP addresses</span></span>

<span data-ttu-id="b7fe1-124">設定程式的第二個步驟是先新增所需的網域，然後新增 Skype 會議廣播所需的 IP 位址和 URL 才能工作。</span><span class="sxs-lookup"><span data-stu-id="b7fe1-124">The second step in the setup process is for you to first add domains that are needed and then add IP addresses and URLs that are required for Skype Meeting Broadcast to work.</span></span>

- <span data-ttu-id="b7fe1-125">**在這裡查看哪些是** 必填的 Skype Online 端點 URL 和 IP 位址，以新增所需的 [Skype Online 端點 URL 和 IP 位址](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo)。</span><span class="sxs-lookup"><span data-stu-id="b7fe1-125">**Add the required Skype for Business Online endpoint URLs and IP addresses by seeing which ones are required** [here](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo).</span></span>

## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a><span data-ttu-id="b7fe1-126">在混合式部署和組織中設定 Skype 會議廣播</span><span class="sxs-lookup"><span data-stu-id="b7fe1-126">Set up Skype Meeting Broadcast in Hybrid deployments and organizations</span></span>

<span data-ttu-id="b7fe1-127">如果您有商務用 Skype Online 組織，以及 Lync Server 2010、Microsoft Lync Server 2013 和商務用 Skype Server 2015 的內部部署，而且有線上和內部部署的使用者，除了上述設定步驟之外，您還需要執行其他設定步驟，讓內部部署組織能夠與商務用 Skype Online 通訊，並允許所有使用者加入 Skype 會議廣播。</span><span class="sxs-lookup"><span data-stu-id="b7fe1-127">If you have a Skype for Business Online organization and an on-premises deployment of Lync Server 2010, Microsoft Lync Server 2013, and Skype for Business Server 2015 and have users both online and on-premises, there are other setup steps that you will need to do in addition to the ones above to enable your on-premises organization to communicate with Skype for Business Online and allow all your users to join a Skype Meeting Broadcast.</span></span> <span data-ttu-id="b7fe1-128">若要瞭解這些要求是什麼，請參閱設定 Skype 會議廣播 [的內部](../../SfbServer/deploy/configure-skype-meeting-broadcast.md)部署。</span><span class="sxs-lookup"><span data-stu-id="b7fe1-128">To see what those requirements are, see [Configure your on-premises deployment for Skype Meeting Broadcast](../../SfbServer/deploy/configure-skype-meeting-broadcast.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="b7fe1-129">相關主題</span><span class="sxs-lookup"><span data-stu-id="b7fe1-129">Related topics</span></span>

[<span data-ttu-id="b7fe1-130">啟用 Skype 會議廣播</span><span class="sxs-lookup"><span data-stu-id="b7fe1-130">Enable Skype Meeting Broadcast</span></span>](enable-skype-meeting-broadcast.md)

[<span data-ttu-id="b7fe1-131">Office 365 URL 與 IP 位址範圍</span><span class="sxs-lookup"><span data-stu-id="b7fe1-131">Office 365 URLs and IP address ranges</span></span>](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[<span data-ttu-id="b7fe1-132">設定商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="b7fe1-132">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)