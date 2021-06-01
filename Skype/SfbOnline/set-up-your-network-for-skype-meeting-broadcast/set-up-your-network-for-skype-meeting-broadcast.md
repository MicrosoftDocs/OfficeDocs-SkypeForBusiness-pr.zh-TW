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
description: 瞭解 Skype Online 的 商務用 Skype 會議廣播功能，此功能可讓您排程、製作會議或活動，以及將會議或活動廣播給最多 10，000 位出席者的大型線上觀眾。
ms.openlocfilehash: da27110313765bb50df92e3bafb6f09ceae5f301
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237549"
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a><span data-ttu-id="60698-103">為您的 Skype 會議廣播設定網路</span><span class="sxs-lookup"><span data-stu-id="60698-103">Set up your network for Skype Meeting Broadcast</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="60698-104">啟用會議[Skype廣播](enable-skype-meeting-broadcast.md)Skype會議廣播之後，您需要設定您的網路。</span><span class="sxs-lookup"><span data-stu-id="60698-104">After you [Enable Skype Meeting Broadcast](enable-skype-meeting-broadcast.md) Skype Meeting Broadcast, you need to configure your network.</span></span> <span data-ttu-id="60698-105">如果您想要為公司外部人員舉辦網路研討會和其他廣播，請執行此步驟。</span><span class="sxs-lookup"><span data-stu-id="60698-105">Do this step if you want to hold webinars and other broadcasts for people outside of your business.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="60698-106">商務用 SkypeOnline 將于 2021 年 7 月 31 日終止服務存取權。</span><span class="sxs-lookup"><span data-stu-id="60698-106">Skype for Business Online is retiring on July 31, 2021, at which time access to the service will end.</span></span> <span data-ttu-id="60698-107">我們鼓勵客戶開始升級至 Microsoft Teams 中通訊和團隊合作的核心用戶端 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="60698-107">We encourage customers to begin the upgrade to Microsoft Teams, the core client for communications and teamwork in Microsoft 365.</span></span>

<span data-ttu-id="60698-108">如果您沒有防火牆的組組經驗，請考慮雇用 [Microsoft 合作夥伴](https://go.microsoft.com/fwlink/?linkid=391089) 來執行此步驟。</span><span class="sxs-lookup"><span data-stu-id="60698-108">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>

<span data-ttu-id="60698-109">若要略過此步驟，改為將另一個企業新增到您的聯盟，以便邀請他們加入廣播，請遵循允許使用者與外部使用者商務用 Skype[中的步驟](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)。</span><span class="sxs-lookup"><span data-stu-id="60698-109">To skip this step and instead add another business to your federation so you can invite them to broadcasts, follow the steps in [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span>

## <a name="step-1-set-up-allowed-domains"></a><span data-ttu-id="60698-110">步驟 1：設定允許的網域</span><span class="sxs-lookup"><span data-stu-id="60698-110">Step 1: Set up allowed domains</span></span>

<span data-ttu-id="60698-111">使用 **下列** 其中一種方法來設定允許的網域：</span><span class="sxs-lookup"><span data-stu-id="60698-111">Use **one** of the following methods to set up allowed domains:</span></span>

## #

 <span data-ttu-id="60698-112">**方法 1：使用系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="60698-112">**Method 1: Use the admin center**</span></span>

1. <span data-ttu-id="60698-113">請前往系統管理中心，然後在左側導航區中，設定  >  **[服務 &amp; 設定，** 然後選擇 [商務用 Skype。 </span><span class="sxs-lookup"><span data-stu-id="60698-113">Go to the admin center and then in the left nav, click **Settings** > **Services &amp; add-ins**, and then choose **Skype for Business**.</span></span>

2. <span data-ttu-id="60698-114">在外部 **共用** 頁面上的網域例外情形下，選取 所有網域都受到封鎖，然後輸入下列網域，以逗號分隔 (，) ：</span><span class="sxs-lookup"><span data-stu-id="60698-114">On the **External sharing** page under **Domain exceptions**, select **All domains are blocked except**, and enter the following domains, separated with a comma (,):</span></span>

   - <span data-ttu-id="60698-115">noammeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="60698-115">noammeetings.lync.com</span></span>

   - <span data-ttu-id="60698-116">emeameetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="60698-116">emeameetings.lync.com</span></span>

   - <span data-ttu-id="60698-117">apacmeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="60698-117">apacmeetings.lync.com</span></span>

   - <span data-ttu-id="60698-118">resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="60698-118">resources.lync.com</span></span>

3. <span data-ttu-id="60698-119">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="60698-119">Click **Save**.</span></span>

## #

 <span data-ttu-id="60698-120">**方法 2：使用Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="60698-120">**Method 2: Use Windows PowerShell**</span></span>

- <span data-ttu-id="60698-121">在 [**開始功能表上**， 以滑鼠右鍵按一下 **Windows PowerShell** 然後按一下 **[以系統管理員的執行**> 。</span><span class="sxs-lookup"><span data-stu-id="60698-121">From the **Start Menu**, right-click **Windows PowerShell** and click **Run as administrator**.</span></span> <span data-ttu-id="60698-122">在 **Windows PowerShell視窗中**，輸入每一行，然後按 Enter。</span><span class="sxs-lookup"><span data-stu-id="60698-122">In the **Windows PowerShell** window, type each line and press Enter.</span></span>

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

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a><span data-ttu-id="60698-123">步驟 2：新增Skype廣播網域、URL 和 IP 位址</span><span class="sxs-lookup"><span data-stu-id="60698-123">Step 2: Add Skype Meeting Broadcast domains, URLs, and IP addresses</span></span>

<span data-ttu-id="60698-124">設定程式的第二個步驟是先新增所需的網域，然後新增讓會議廣播Skype所需的 IP 位址和 URL。</span><span class="sxs-lookup"><span data-stu-id="60698-124">The second step in the setup process is for you to first add domains that are needed and then add IP addresses and URLs that are required for Skype Meeting Broadcast to work.</span></span>

- <span data-ttu-id="60698-125">**在這裡查看商務用 Skype** Web 端點 URL 和 IP 位址，以新增所需的 [連線端點 URL 和 IP 位址](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo)。</span><span class="sxs-lookup"><span data-stu-id="60698-125">**Add the required Skype for Business Online endpoint URLs and IP addresses by seeing which ones are required** [here](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo).</span></span>

## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a><span data-ttu-id="60698-126">在混合式部署Skype組織中設定會議廣播</span><span class="sxs-lookup"><span data-stu-id="60698-126">Set up Skype Meeting Broadcast in Hybrid deployments and organizations</span></span>

<span data-ttu-id="60698-127">如果您有 商務用 Skype Online 組織，以及 Lync Server 2010、Microsoft Lync Server 2013 和 商務用 Skype Server 2015 內部部署，而且有線上和內部部署的使用者，除了上述設定步驟之外，您還需要執行其他設定步驟，讓內部部署組織能夠與 商務用 Skype Online 通訊，並允許所有使用者加入 Skype 會議廣播。</span><span class="sxs-lookup"><span data-stu-id="60698-127">If you have a Skype for Business Online organization and an on-premises deployment of Lync Server 2010, Microsoft Lync Server 2013, and Skype for Business Server 2015 and have users both online and on-premises, there are other setup steps that you will need to do in addition to the ones above to enable your on-premises organization to communicate with Skype for Business Online and allow all your users to join a Skype Meeting Broadcast.</span></span> <span data-ttu-id="60698-128">若要瞭解這些要求是什麼，請參閱為會議廣播設定Skype[部署](../../SfbServer/deploy/configure-skype-meeting-broadcast.md)。</span><span class="sxs-lookup"><span data-stu-id="60698-128">To see what those requirements are, see [Configure your on-premises deployment for Skype Meeting Broadcast](../../SfbServer/deploy/configure-skype-meeting-broadcast.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="60698-129">相關主題</span><span class="sxs-lookup"><span data-stu-id="60698-129">Related topics</span></span>

[<span data-ttu-id="60698-130">啟用 Skype 會議廣播</span><span class="sxs-lookup"><span data-stu-id="60698-130">Enable Skype Meeting Broadcast</span></span>](enable-skype-meeting-broadcast.md)

[<span data-ttu-id="60698-131">Office 365 URL 與 IP 位址範圍</span><span class="sxs-lookup"><span data-stu-id="60698-131">Office 365 URLs and IP address ranges</span></span>](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[<span data-ttu-id="60698-132">設定商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="60698-132">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
