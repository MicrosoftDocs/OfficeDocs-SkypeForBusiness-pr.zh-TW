---
title: 應用程式中的 Walkie Talkie Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: 如何從 ITAdmin 的觀點，在 Microsoft Teams中設定 Walkie Talkie 應用程式。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9f86d40772eb067a561708c6170ef2354bae521b
ms.sourcegitcommit: 05411575d07d3eadc79d872d1cf81b36aae25621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/13/2021
ms.locfileid: "52479070"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a><span data-ttu-id="bd770-103">在應用程式中的對講Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bd770-103">Walkie Talkie app in Microsoft Teams</span></span>

<span data-ttu-id="bd770-104">Android 中的對講Teams App 提供即時隨 (PTT) 通訊功能，現在可在 Android 上使用。</span><span class="sxs-lookup"><span data-stu-id="bd770-104">The Walkie Talkie app in Teams provides instant push-to-talk (PTT) communication for your team and is now available on Android.</span></span> <span data-ttu-id="bd770-105">Walkie Talkie 允許使用者使用他們成員相同的基礎通道，與小組聯繫。</span><span class="sxs-lookup"><span data-stu-id="bd770-105">Walkie Talkie allows users to connect with their team using the same underlying channels they're members of.</span></span> <span data-ttu-id="bd770-106">只有在頻道中連接到 Walkie Talkie 的使用者才能成為參與者，而且可以一次一個地使用隨推式交談來彼此通訊。</span><span class="sxs-lookup"><span data-stu-id="bd770-106">Only users who connect to Walkie Talkie in a channel become participants and can communicate with each other using push-to-talk, one at a time.</span></span>

<span data-ttu-id="bd770-107">使用 Teams 中的 Walkie Talkie，前線員工現在可以安全地使用熟悉的 PTT 體驗進行通訊，而不需要攜帶大量收音機，而 Walkie Talkie 可在任何位置使用 WiFi 或行動電話網際網路連接。</span><span class="sxs-lookup"><span data-stu-id="bd770-107">With Walkie Talkie in Teams, Frontline workers can now securely communicate with a familiar PTT experience without needing to carry bulky radios, and Walkie Talkie works anywhere with WiFi or cellular internet connectivity.</span></span>

## <a name="getting-started"></a><span data-ttu-id="bd770-108">快速入門</span><span class="sxs-lookup"><span data-stu-id="bd770-108">Getting started</span></span>

### <a name="deploying-walkie-talkie"></a><span data-ttu-id="bd770-109">部署對講臺 Talkie</span><span class="sxs-lookup"><span data-stu-id="bd770-109">Deploying Walkie Talkie</span></span>

<span data-ttu-id="bd770-110">目前，Walkie Talkie 適用于使用 Google 行動服務 (GMS) 且尚未預先安裝的 Android 裝置。</span><span class="sxs-lookup"><span data-stu-id="bd770-110">Currently, Walkie Talkie is available for Android devices with Google Mobile Services (GMS) and is not pre-installed.</span></span> <span data-ttu-id="bd770-111">若要為貴組織的使用者啟用這項功能，您必須將 Walkie Talkie 新增到 [](teams-app-setup-policies.md)從系統管理中心指派給使用者的應用程式設定Teams   [策略](https://admin.teams.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="bd770-111">To enable this feature for users in your organization, you need to add Walkie Talkie to the [App Setup Policy](teams-app-setup-policies.md) assigned to users from the [Teams Admin Center](https://admin.teams.microsoft.com/).</span></span> <span data-ttu-id="bd770-112">啟用後，Walkie Talkie 將在 48 小時內在 Android App 上提供。</span><span class="sxs-lookup"><span data-stu-id="bd770-112">Once enabled, Walkie Talkie will become available on the Android app within 48 hours.</span></span>

### <a name="adding-walkie-talkie-to-your-app-list"></a><span data-ttu-id="bd770-113">將 Walkie Talkie 新加入您的應用程式清單</span><span class="sxs-lookup"><span data-stu-id="bd770-113">Adding Walkie Talkie to your app list</span></span>

<span data-ttu-id="bd770-114">在 Microsoft Teams系統管理中心，Teams **應用程式** 設定政策下，您應該將允許  >  \*\*\*\*\*\*使用者釘\*\* 點設定為 **On**。</span><span class="sxs-lookup"><span data-stu-id="bd770-114">In the Microsoft Teams admin center, under **Teams app** > **Setup policies**, you should have **Allow user pinning** set to **On**.</span></span> <span data-ttu-id="bd770-115">接著，在 [釘上的應用程式> 區段下，按一下 **[+新增應用程式>**。</span><span class="sxs-lookup"><span data-stu-id="bd770-115">Then, under the Pinned Apps section, click **+Add Apps**.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-1.png" alt-text="顯示要選取的已釘選應用程式區段和新增應用程式按鈕。":::

<span data-ttu-id="bd770-117">在右側 **出現的新增釘** 上應用程式面板上，使用搜尋文字方塊尋找Walkie Talkie。</span><span class="sxs-lookup"><span data-stu-id="bd770-117">On the **Add pinned apps** panel that appears on the right, use the **Search** textbox to look for Walkie Talkie.</span></span> <span data-ttu-id="bd770-118">當您將名稱做為搜尋結果時，請選取名稱右邊的新增按鈕，將其新加到清單中。</span><span class="sxs-lookup"><span data-stu-id="bd770-118">When you have it as a search result, select the **Add** button to the right of the name to add it to your list.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="顯示在搜尋窗格中輸入 Walkie 的已釘選應用程式側邊欄，以及搜尋結果中的 Walkie Talkie 應用程式，旁邊有新增按鈕。":::

<span data-ttu-id="bd770-120">Walkie Talkie App 現在應該會出現在 [釘選的 App> 清單中，而且一旦按一下 [儲存） 按鈕 **即可使用。**</span><span class="sxs-lookup"><span data-stu-id="bd770-120">The Walkie Talkie app should now appear on the Pinned Apps list, and be available for use once you click the **Save** button.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-3.png" alt-text="顯示已新增 Walkie Talkie 應用程式的釘選應用程式清單，以及清單下方的儲存按鈕。":::

### <a name="network-documentation"></a><span data-ttu-id="bd770-122">網路檔</span><span class="sxs-lookup"><span data-stu-id="bd770-122">Network documentation</span></span>

<span data-ttu-id="bd770-123">Teams對講Teams需要網際網路連接，且網路條件低於網路條件才能獲得最佳體驗。</span><span class="sxs-lookup"><span data-stu-id="bd770-123">Walkie Talkie in Teams requires Internet connectivity and below the network conditions are required for optimal experience.</span></span>

|<span data-ttu-id="bd770-124">度量</span><span class="sxs-lookup"><span data-stu-id="bd770-124">Metric</span></span> | <span data-ttu-id="bd770-125">必要</span><span class="sxs-lookup"><span data-stu-id="bd770-125">Required</span></span> |
|---|---|
|<span data-ttu-id="bd770-126">RTT (延遲) </span><span class="sxs-lookup"><span data-stu-id="bd770-126">Latency (RTT)</span></span> | <span data-ttu-id="bd770-127">< 300 毫秒</span><span class="sxs-lookup"><span data-stu-id="bd770-127">< 300ms</span></span> |
|<span data-ttu-id="bd770-128">抖動</span><span class="sxs-lookup"><span data-stu-id="bd770-128">Jitter</span></span> |<span data-ttu-id="bd770-129">< 30 毫秒</span><span class="sxs-lookup"><span data-stu-id="bd770-129">< 30ms</span></span> |
|<span data-ttu-id="bd770-130">封包遺失</span><span class="sxs-lookup"><span data-stu-id="bd770-130">Packet Loss</span></span> |<span data-ttu-id="bd770-131">< 1%</span><span class="sxs-lookup"><span data-stu-id="bd770-131">< 1%</span></span> |

<span data-ttu-id="bd770-132">如上所述，IP 網路即時媒體的品質受到網路連接品質的嚴重影響，尤其是受到以下數量的影響：</span><span class="sxs-lookup"><span data-stu-id="bd770-132">As noted above, the quality of real-time media over an IP network is greatly impacted by the quality of the network connectivity, but especially by the amount of:</span></span>

- <span data-ttu-id="bd770-133">**延遲** - 這是從 A 點到網路 B 點取得 IP 封包所花的時間。</span><span class="sxs-lookup"><span data-stu-id="bd770-133">**Latency** - This is the time it takes to get an IP packet from point A to point B on the network.</span></span> <span data-ttu-id="bd770-134">此網路傳播延遲基本上與兩點之間的實體距離和光速有關，包括介於兩者之間的各種路由器所增加的負荷。</span><span class="sxs-lookup"><span data-stu-id="bd770-134">This network propagation delay is essentially tied to physical distance between the two points and the speed of light, including more overhead taken by the various routers in between.</span></span> <span data-ttu-id="bd770-135">延遲是以 RTT (的往返時間) 。</span><span class="sxs-lookup"><span data-stu-id="bd770-135">Latency is measured as Round-trip Time (RTT).</span></span>
- <span data-ttu-id="bd770-136">**到達間抖動** - 這是連續封包之間延遲的平均變化。</span><span class="sxs-lookup"><span data-stu-id="bd770-136">**Inter-Arrival Jitter** - This is the average change in delay between successive packets.</span></span>
- <span data-ttu-id="bd770-137">**封包** 遺失 - 這通常定義為在給定時段內遺失的封包百分比。</span><span class="sxs-lookup"><span data-stu-id="bd770-137">**Packet Loss** - This is often defined as a percentage of packets that are lost in a given window of time.</span></span> <span data-ttu-id="bd770-138">封包遺失會直接影響音訊品質，包括小型、個別遺失的封包幾乎沒有影響，以及造成音訊完全中斷的背對背斷流損失。</span><span class="sxs-lookup"><span data-stu-id="bd770-138">Packet loss directly affects audio quality—from small, individual lost packets having almost no impact, to back-to-back burst losses that cause complete audio cut-out.</span></span>

<span data-ttu-id="bd770-139">在傳送或接收音訊時，Walkie Talkie 的預期資料使用量約為 20 Kb/s。</span><span class="sxs-lookup"><span data-stu-id="bd770-139">Expected data usage from Walkie Talkie is around 20 Kb/s when sending or receiving audio.</span></span> <span data-ttu-id="bd770-140">閒置時，Walkie Talkie 的預期資料使用量是可忽略的。</span><span class="sxs-lookup"><span data-stu-id="bd770-140">When idle, expected data usage from Walkie Talkie is negligible.</span></span>

### <a name="walkie-talkie-devices"></a><span data-ttu-id="bd770-141">對講臺對講裝置</span><span class="sxs-lookup"><span data-stu-id="bd770-141">Walkie Talkie devices</span></span>

<span data-ttu-id="bd770-142">即使電話已鎖定，前線員工也經常需要說話並接聽 Walkie Talkie 通話。</span><span class="sxs-lookup"><span data-stu-id="bd770-142">Frontline workers often need to speak and receive Walkie Talkie calls even when their phones are locked.</span></span> <span data-ttu-id="bd770-143">透過具有專用 PTT 按鈕的專用裝置，即可獲得此體驗。</span><span class="sxs-lookup"><span data-stu-id="bd770-143">This experience is possible through specialized devices with a dedicated PTT button.</span></span>

- <span data-ttu-id="bd770-144">**耳機**</span><span class="sxs-lookup"><span data-stu-id="bd770-144">**Headsets**</span></span>
  - <span data-ttu-id="bd770-145">無線耳機</span><span class="sxs-lookup"><span data-stu-id="bd770-145">Wireless headsets</span></span> 
    - [<span data-ttu-id="bd770-146">BlueParrott</span><span class="sxs-lookup"><span data-stu-id="bd770-146">BlueParrott</span></span>](https://www.blueparrott.com/microsoft-teams-walkie-talkie)
  - <span data-ttu-id="bd770-147">有線耳機</span><span class="sxs-lookup"><span data-stu-id="bd770-147">Wired headsets</span></span> 
    - [<span data-ttu-id="bd770-148">克洛因電子</span><span class="sxs-lookup"><span data-stu-id="bd770-148">Klein Electronics</span></span>](https://www.kleinelectronics.com/poc-accessories/mtwt/)
- <span data-ttu-id="bd770-149">**強固型手機**</span><span class="sxs-lookup"><span data-stu-id="bd770-149">**Rugged phones**</span></span>
  - <span data-ttu-id="bd770-150">Samsung [Galaxy XCover Pro](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/)， [Galaxy XCover 5，](https://www.samsung.com/de/smartphones/others/galaxy-xcover-5-black-64gb-sm-g525fzkdeeb/buy) [Galaxy Tab Active 3](https://www.samsung.com/us/business/tablets/galaxy-tab-active/buy/)</span><span class="sxs-lookup"><span data-stu-id="bd770-150">Samsung [Galaxy XCover Pro](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/), [Galaxy XCover 5](https://www.samsung.com/de/smartphones/others/galaxy-xcover-5-black-64gb-sm-g525fzkdeeb/buy), [Galaxy Tab Active 3](https://www.samsung.com/us/business/tablets/galaxy-tab-active/buy/)</span></span>
    -  <span data-ttu-id="bd770-151">手動設定 - 安裝Teams之後，流覽至 設定 > XCover/Active 鍵>進>功能。</span><span class="sxs-lookup"><span data-stu-id="bd770-151">Manual setup - With Teams installed, navigate to Settings > Advanced Features > XCover/Active key.</span></span> <span data-ttu-id="bd770-152">開啟 '使用 App 控制 XCover 鍵'，然後選取 Teams'</span><span class="sxs-lookup"><span data-stu-id="bd770-152">Turn on 'Control XCover key with app' and select 'Teams'</span></span>
    -  [<span data-ttu-id="bd770-153">MDM 設定</span><span class="sxs-lookup"><span data-stu-id="bd770-153">MDM setup</span></span>](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm)

> [!NOTE]
> <span data-ttu-id="bd770-154">這些裝置未通過Teams認證。</span><span class="sxs-lookup"><span data-stu-id="bd770-154">These devices are not Teams certified.</span></span> <span data-ttu-id="bd770-155">它們已經過驗證，Teams Walkie Talkie 使用。</span><span class="sxs-lookup"><span data-stu-id="bd770-155">They have been validated to work with Teams Walkie Talkie.</span></span>

### <a name="license-requirements"></a><span data-ttu-id="bd770-156">授權需求</span><span class="sxs-lookup"><span data-stu-id="bd770-156">License requirements</span></span>

<span data-ttu-id="bd770-157">Walkie Talkie 應用程式會包含在所有付費授權Teams訂閱Office 365[中](/office365/servicedescriptions/teams-service-description)。</span><span class="sxs-lookup"><span data-stu-id="bd770-157">Walkie Talkie app is included in all paid licenses of Teams in [Office 365 subscriptions](/office365/servicedescriptions/teams-service-description).</span></span> <span data-ttu-id="bd770-158">若要進一Teams，請參閱如何 [存取Microsoft Teams？](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)</span><span class="sxs-lookup"><span data-stu-id="bd770-158">For more information about getting Teams, check out [How do I get access to Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)?</span></span>

> [!NOTE]
> <span data-ttu-id="bd770-159">某些進位功能可能需要額外授權。</span><span class="sxs-lookup"><span data-stu-id="bd770-159">Certain advanced features may require additional licensing.</span></span> <span data-ttu-id="bd770-160">例如，與 Samsung Galaxy XCover Pro需要 Knx 授權。</span><span class="sxs-lookup"><span data-stu-id="bd770-160">For example, integration with Samsung Galaxy XCover Pro requires a Knox license.</span></span>

## <a name="further-information"></a><span data-ttu-id="bd770-161">進一步資訊</span><span class="sxs-lookup"><span data-stu-id="bd770-161">Further information</span></span>

- <span data-ttu-id="bd770-162">ITAdmins 可以透過應用程式政策，維持對講臺對講程式消費者控制權。</span><span class="sxs-lookup"><span data-stu-id="bd770-162">ITAdmins can maintain control over who is using Walkie Talkie through App Policies.</span></span>
- <span data-ttu-id="bd770-163">如果您的前線員工使用行動資料透過 Teams 通訊，Walkie Talkie 會使用相同的方法。</span><span class="sxs-lookup"><span data-stu-id="bd770-163">If your Frontline worker is using mobile data to communicate via Teams, Walkie Talkie will use the same method.</span></span>
- <span data-ttu-id="bd770-164">對講機應能順利在低頻寬情況下，或智慧型手機已連接及使用的情況中順利使用。</span><span class="sxs-lookup"><span data-stu-id="bd770-164">Walkie Talkie should work well in low bandwidth situations, or situations where your smartphone is connected and working.</span></span> <span data-ttu-id="bd770-165">當完全沒有連接時，對講臺 Talkie 將無法工作。</span><span class="sxs-lookup"><span data-stu-id="bd770-165">Walkie Talkie will not work when there is no connectivity at all.</span></span>

<span data-ttu-id="bd770-166">有關使用者體驗的進一步閱讀，請參閱：</span><span class="sxs-lookup"><span data-stu-id="bd770-166">For further reading on the end-user experience, see:</span></span>

- [<span data-ttu-id="bd770-167">開始使用 walkie Talkie Teams Talkie</span><span class="sxs-lookup"><span data-stu-id="bd770-167">Get started with Teams Walkie Talkie</span></span>](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [<span data-ttu-id="bd770-168">使用 Walkie Talkie 與小組溝通</span><span class="sxs-lookup"><span data-stu-id="bd770-168">Communicate with your team with Walkie Talkie</span></span>](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
