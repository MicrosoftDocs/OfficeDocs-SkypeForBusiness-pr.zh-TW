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
description: 瞭解商務用 Skype Online 的 Skype 會議廣播功能，可讓您安排、產生及廣播會議或事件給最多10000出席者的大型線上使用者。
ms.openlocfilehash: b774c368674f421c11f36339ef7188ea8de82e64
ms.sourcegitcommit: ab566ddab9d26440bac1716a975f30e075d0c7b5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/14/2021
ms.locfileid: "49865157"
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a><span data-ttu-id="c59e4-103">為您的 Skype 會議廣播設定網路</span><span class="sxs-lookup"><span data-stu-id="c59e4-103">Set up your network for Skype Meeting Broadcast</span></span>

<span data-ttu-id="c59e4-104">在您 [啟用 Skype 會議廣播](enable-skype-meeting-broadcast.md) Skype 會議廣播之後，您必須設定您的網路。</span><span class="sxs-lookup"><span data-stu-id="c59e4-104">After you [Enable Skype Meeting Broadcast](enable-skype-meeting-broadcast.md) Skype Meeting Broadcast, you need to configure your network.</span></span> <span data-ttu-id="c59e4-105">如果您想要為企業外部的人員舉行網路研討會和其他廣播，請執行此步驟。</span><span class="sxs-lookup"><span data-stu-id="c59e4-105">Do this step if you want to hold webinars and other broadcasts for people outside of your business.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c59e4-106">商務用 Skype Online 已于2021年7月31日停用，此時將會結束存取服務的時間。</span><span class="sxs-lookup"><span data-stu-id="c59e4-106">Skype for Business Online is retiring on July 31, 2021, at which time access to the service will end.</span></span> <span data-ttu-id="c59e4-107">我們鼓勵客戶開始升級至 Microsoft 團隊，即在 Microsoft 365 中進行通訊與團隊合作的核心用戶端。</span><span class="sxs-lookup"><span data-stu-id="c59e4-107">We encourage customers to begin the upgrade to Microsoft Teams, the core client for communications and teamwork in Microsoft 365.</span></span>

<span data-ttu-id="c59e4-108">如果您不熟悉如何設定防火牆，請考慮聘用 [Microsoft 合作夥伴](https://go.microsoft.com/fwlink/?linkid=391089) 來為您執行此步驟。</span><span class="sxs-lookup"><span data-stu-id="c59e4-108">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>

<span data-ttu-id="c59e4-109">若要略過此步驟，而改為將其他公司新增到您的同盟，以便邀請他們進行廣播，請依照 [允許使用者聯繫外部商務用 Skype 使用者](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)的步驟操作。</span><span class="sxs-lookup"><span data-stu-id="c59e4-109">To skip this step and instead add another business to your federation so you can invite them to broadcasts, follow the steps in [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span>

## <a name="step-1-set-up-allowed-domains"></a><span data-ttu-id="c59e4-110">步驟1：設定允許的網域</span><span class="sxs-lookup"><span data-stu-id="c59e4-110">Step 1: Set up allowed domains</span></span>

<span data-ttu-id="c59e4-111">使用下列 **其中一** 種方法來設定 [允許的網域]：</span><span class="sxs-lookup"><span data-stu-id="c59e4-111">Use **one** of the following methods to set up allowed domains:</span></span>

## #

 <span data-ttu-id="c59e4-112">**方法1：使用系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="c59e4-112">**Method 1: Use the admin center**</span></span>

1. <span data-ttu-id="c59e4-113">移至系統管理中心，然後在左導覽中，按一下 [**設定**  >  **服務 &amp; 增益集**]，然後選擇 [**商務用 Skype**]。</span><span class="sxs-lookup"><span data-stu-id="c59e4-113">Go to the admin center and then in the left nav, click **Settings** > **Services &amp; add-ins**, and then choose **Skype for Business**.</span></span>

2. <span data-ttu-id="c59e4-114">在 [ **外部共用** ] 頁面上的 [ **網域例外**] 底下，選取 [ **除了] 以外的所有網域**，然後輸入下列網域，並以逗號 ( ) ：</span><span class="sxs-lookup"><span data-stu-id="c59e4-114">On the **External sharing** page under **Domain exceptions**, select **All domains are blocked except**, and enter the following domains, separated with a comma (,):</span></span>

   - <span data-ttu-id="c59e4-115">noammeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="c59e4-115">noammeetings.lync.com</span></span>

   - <span data-ttu-id="c59e4-116">emeameetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="c59e4-116">emeameetings.lync.com</span></span>

   - <span data-ttu-id="c59e4-117">apacmeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="c59e4-117">apacmeetings.lync.com</span></span>

   - <span data-ttu-id="c59e4-118">resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="c59e4-118">resources.lync.com</span></span>

3. <span data-ttu-id="c59e4-119">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="c59e4-119">Click **Save**.</span></span>

## #

 <span data-ttu-id="c59e4-120">**方法2：使用 Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="c59e4-120">**Method 2: Use Windows PowerShell**</span></span>

- <span data-ttu-id="c59e4-121">從 [ **開始] 功能表**，以滑鼠右鍵按一下 [ **Windows PowerShell** ]，然後按一下 [ **以系統管理員身分執行**]。</span><span class="sxs-lookup"><span data-stu-id="c59e4-121">From the **Start Menu**, right-click **Windows PowerShell** and click **Run as administrator**.</span></span> <span data-ttu-id="c59e4-122">在 [ **Windows PowerShell** ] 視窗中，輸入每一行，然後按 enter 鍵。</span><span class="sxs-lookup"><span data-stu-id="c59e4-122">In the **Windows PowerShell** window, type each line and press Enter.</span></span>

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

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a><span data-ttu-id="c59e4-123">步驟2：新增 Skype 會議廣播網域、Url 和 IP 位址</span><span class="sxs-lookup"><span data-stu-id="c59e4-123">Step 2: Add Skype Meeting Broadcast domains, URLs, and IP addresses</span></span>

<span data-ttu-id="c59e4-124">安裝程式中的第二個步驟是您首先要新增所需的網域，然後新增 Skype 會議廣播所需的 IP 位址和 Url 才能正常運作。</span><span class="sxs-lookup"><span data-stu-id="c59e4-124">The second step in the setup process is for you to first add domains that are needed and then add IP addresses and URLs that are required for Skype Meeting Broadcast to work.</span></span>

- <span data-ttu-id="c59e4-125">[在這裡](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo)**查看需要的商務用 Skype Online 端點 url 和 IP 位址**。</span><span class="sxs-lookup"><span data-stu-id="c59e4-125">**Add the required Skype for Business Online endpoint URLs and IP addresses by seeing which ones are required** [here](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo).</span></span>

## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a><span data-ttu-id="c59e4-126">在混合式部署與組織中設定 Skype 會議廣播</span><span class="sxs-lookup"><span data-stu-id="c59e4-126">Set up Skype Meeting Broadcast in Hybrid deployments and organizations</span></span>

<span data-ttu-id="c59e4-127">如果您有商務用 Skype Online 組織與內部部署的 Lync Server 2010，Microsoft Lync Server 2013 和商務用 Skype Server 2015，且使用者都在線上和內部部署中，除了上述步驟之外，還需要執行其他設定步驟，才能讓您的內部部署組織與商務用 Skype Online 進行通訊，並允許您的所有使用者加入 Skype 會議廣播。</span><span class="sxs-lookup"><span data-stu-id="c59e4-127">If you have a Skype for Business Online organization and an on-premises deployment of Lync Server 2010, Microsoft Lync Server 2013, and Skype for Business Server 2015 and have users both online and on-premises, there are other setup steps that you will need to do in addition to the ones above to enable your on-premises organization to communicate with Skype for Business Online and allow all your users to join a Skype Meeting Broadcast.</span></span> <span data-ttu-id="c59e4-128">若要查看這些需求，請參閱 [設定 Skype 會議廣播的內部部署部署](https://go.microsoft.com/fwlink/?LinkId=617070)。</span><span class="sxs-lookup"><span data-stu-id="c59e4-128">To see what those requirements are, see [Configure your on-premises deployment for Skype Meeting Broadcast](https://go.microsoft.com/fwlink/?LinkId=617070).</span></span>

## <a name="related-topics"></a><span data-ttu-id="c59e4-129">相關主題</span><span class="sxs-lookup"><span data-stu-id="c59e4-129">Related topics</span></span>

[<span data-ttu-id="c59e4-130">啟用 Skype 會議廣播</span><span class="sxs-lookup"><span data-stu-id="c59e4-130">Enable Skype Meeting Broadcast</span></span>](enable-skype-meeting-broadcast.md)

[<span data-ttu-id="c59e4-131">Office 365 URL 與 IP 位址範圍</span><span class="sxs-lookup"><span data-stu-id="c59e4-131">Office 365 URLs and IP address ranges</span></span>](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[<span data-ttu-id="c59e4-132">設定商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="c59e4-132">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)



