---
title: Microsoft 團隊中的 Walkie Talkie 應用程式
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: 如何在 Microsoft 團隊中從 ITAdmin 的觀點來設定 Walkie Talkie 應用程式。
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
ms.openlocfilehash: 4154a3ad30bf18de934f0fe5a23bbabc94fc76eb
ms.sourcegitcommit: 863347fb6e5916d8d936adc4ddcebb2e32a91d1c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/22/2020
ms.locfileid: "45229049"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a><span data-ttu-id="b49ac-103">Microsoft 團隊中的 Walkie Talkie 應用程式</span><span class="sxs-lookup"><span data-stu-id="b49ac-103">Walkie Talkie app in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="b49ac-104">團隊中的 Walkie Talkie 應用程式可為您的小組提供立即推播（PTT）通訊，且可在 Android 上公開預覽。</span><span class="sxs-lookup"><span data-stu-id="b49ac-104">The Walkie Talkie app in Teams provides instant push-to-talk (PTT) communication for your team and is available in Public Preview on Android.</span></span> <span data-ttu-id="b49ac-105">Walkie Talkie 可讓使用者使用其成員的相同基礎頻道與其團隊進行連線。</span><span class="sxs-lookup"><span data-stu-id="b49ac-105">Walkie Talkie allows users to connect with their team using the same underlying channels they're members of.</span></span> <span data-ttu-id="b49ac-106">只有在頻道中連接至 Walkie Talkie 的使用者才會成為參與者，而且可以使用推入式交談與對方進行通訊。</span><span class="sxs-lookup"><span data-stu-id="b49ac-106">Only users who connect to Walkie Talkie in a channel become participants and can communicate with each other using push-to-talk, one at a time.</span></span>

<span data-ttu-id="b49ac-107">在團隊中使用 Walkie Talkie，第一線員工工作者現在可以與熟悉的 PTT 體驗安全地溝通，而不需要攜帶容量龐大的無線電，而且 Walkie Talkie 可在任何地方使用 WiFi 或行動電話網際網路連線。</span><span class="sxs-lookup"><span data-stu-id="b49ac-107">With Walkie Talkie in Teams, firstline workers can now securely communicate with a familiar PTT experience without needing to carry bulky radios, and Walkie Talkie works anywhere with WiFi or cellular internet connectivity.</span></span>

## <a name="getting-started"></a><span data-ttu-id="b49ac-108">快速入門</span><span class="sxs-lookup"><span data-stu-id="b49ac-108">Getting started</span></span>

### <a name="deploying-walkie-talkie"></a><span data-ttu-id="b49ac-109">部署 Walkie Talkie</span><span class="sxs-lookup"><span data-stu-id="b49ac-109">Deploying Walkie Talkie</span></span>

<span data-ttu-id="b49ac-110">在公開預覽版期間，未預先安裝 Walkie Talkie。</span><span class="sxs-lookup"><span data-stu-id="b49ac-110">During the Public Preview, Walkie Talkie is not pre-installed.</span></span> <span data-ttu-id="b49ac-111">若要針對貴組織中的使用者啟用此功能，您必須將 Walkie Talkie 新增 [App Setup Policy](teams-app-setup-policies.md)至   指派給團隊系統[管理中心](https://admin.teams.microsoft.com/)使用者的 App 設定原則。</span><span class="sxs-lookup"><span data-stu-id="b49ac-111">To enable this feature for users in your organization, you need to add Walkie Talkie to the [App Setup Policy](teams-app-setup-policies.md) assigned to users from the [Teams Admin Center](https://admin.teams.microsoft.com/).</span></span>

<span data-ttu-id="b49ac-112">一旦啟用，在48小時內，Android 應用程式就可以使用 Walkie Talkie。</span><span class="sxs-lookup"><span data-stu-id="b49ac-112">Once enabled, Walkie Talkie will become available on the Android app within 48 hours.</span></span>

### <a name="adding-walkie-talkie-to-your-app-list"></a><span data-ttu-id="b49ac-113">將 Walkie Talkie 新增至您的應用程式清單</span><span class="sxs-lookup"><span data-stu-id="b49ac-113">Adding Walkie Talkie to your app list</span></span>

<span data-ttu-id="b49ac-114">在 Microsoft 團隊系統管理中心的 [**團隊 app**  >  **設定原則**] 底下，您應該將 [**允許使用者釘**選] 設為 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="b49ac-114">In the Microsoft Teams admin center, under **Teams app** > **Setup policies**, you should have **Allow user pinning** set to **On**.</span></span> <span data-ttu-id="b49ac-115">接著，在 [固定的 App] 區段底下，按一下 [ **+ 新增 app**]。</span><span class="sxs-lookup"><span data-stu-id="b49ac-115">Then, under the Pinned Apps section, click **+Add Apps**.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-1.png" alt-text="顯示 [固定的 app] 區段以及要選取的 [新增應用程式] 按鈕。":::

<span data-ttu-id="b49ac-117">在右側顯示的 [**新增釘選 app** ] 面板上，使用 [**搜尋**] 文字方塊尋找 Walkie Talkie。</span><span class="sxs-lookup"><span data-stu-id="b49ac-117">On the **Add pinned apps** panel that appears on the right, use the **Search** textbox to look for Walkie Talkie.</span></span> <span data-ttu-id="b49ac-118">當您將它作為搜尋結果時，請按一下名稱右邊的 [**新增**] 按鈕，將其新增至您的清單。</span><span class="sxs-lookup"><span data-stu-id="b49ac-118">When you have it as a search result, click the **Add** button to the right of the name to add it to your list.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="顯示 [新增釘選的 app] 提要欄位，並在搜尋結果中輸入 Walkie 並 Walkie Talkie 應用程式，其旁邊的 [新增] 按鈕。":::

<span data-ttu-id="b49ac-120">Walkie Talkie 應用程式現在應該會出現在釘選的 app 清單中，而且在您按一下 [**儲存**] 按鈕之後就能使用。</span><span class="sxs-lookup"><span data-stu-id="b49ac-120">The Walkie Talkie app should now appear on the Pinned Apps list, and be available for use once you click the **Save** button.</span></span>

:::image type="content" source="media/deploy-walkie-talkie-3.png" alt-text="顯示已新增 [Walkie Talkie] 應用程式的固定 app 清單，以及清單下方的 [儲存] 按鈕。":::

### <a name="network-documentation"></a><span data-ttu-id="b49ac-122">網路檔</span><span class="sxs-lookup"><span data-stu-id="b49ac-122">Network documentation</span></span>

<span data-ttu-id="b49ac-123">小組中的 Walkie Talkie 需要網際網路連線，而且網路條件必須低於最佳體驗。</span><span class="sxs-lookup"><span data-stu-id="b49ac-123">Walkie Talkie in Teams requires Internet connectivity and below the network conditions are required for optimal experience.</span></span>

<span data-ttu-id="b49ac-124">延遲（RTT） < 300ms |抖動 < 30ms |資料包遺失 < 1%</span><span class="sxs-lookup"><span data-stu-id="b49ac-124">Latency (RTT) < 300ms | Jitter < 30ms | Packet Loss < 1%</span></span>

<span data-ttu-id="b49ac-125">如上所述，透過網路連線的品質，即時媒體質量會受到很大的影響，但特別是下列數量：</span><span class="sxs-lookup"><span data-stu-id="b49ac-125">As noted above, the quality of real-time media over an IP network is greatly impacted by the quality of the network connectivity, but especially by the amount of:</span></span>

- <span data-ttu-id="b49ac-126">**延遲**-這是取得 IP 資料包從點 A 到網路上的點 B 所需的時間。</span><span class="sxs-lookup"><span data-stu-id="b49ac-126">**Latency** - This is the time it takes to get an IP packet from point A to point B on the network.</span></span> <span data-ttu-id="b49ac-127">此網路傳播延遲實質上會與兩個點之間的實際距離和光線速度之間的距離產生關聯，包括不同的路由器所佔用的額外負荷。</span><span class="sxs-lookup"><span data-stu-id="b49ac-127">This network propagation delay is essentially tied to physical distance between the two points and the speed of light, including additional overhead taken by the various routers in between.</span></span> <span data-ttu-id="b49ac-128">延遲是以往返時間（RTT）來測定。</span><span class="sxs-lookup"><span data-stu-id="b49ac-128">Latency is measured as Round-trip Time (RTT).</span></span>
- <span data-ttu-id="b49ac-129">**資料包遺失**-通常會定義為在指定的時間視窗中遺失的資料包百分比。</span><span class="sxs-lookup"><span data-stu-id="b49ac-129">**Packet Loss** - This is often defined as a percentage of packets that are lost in a given window of time.</span></span> <span data-ttu-id="b49ac-130">資料包遺失會直接影響音訊品質-從較小、個別遺失且幾乎沒有影響的資料包，到可導致完整音訊切出的後置突發損失。</span><span class="sxs-lookup"><span data-stu-id="b49ac-130">Packet loss directly affects audio quality—from small, individual lost packets having almost no impact, to back-to-back burst losses that cause complete audio cut-out.</span></span>
- <span data-ttu-id="b49ac-131">**抖動**-這是連續資料包之間延遲的平均變更。</span><span class="sxs-lookup"><span data-stu-id="b49ac-131">**Jitter** - This is the average change in delay between successive packets.</span></span>

<span data-ttu-id="b49ac-132">傳送或接收音訊時，Walkie Talkie 的預期資料使用量是在 20KB/s 的周圍。</span><span class="sxs-lookup"><span data-stu-id="b49ac-132">Expected data usage from Walkie Talkie is around 20KB/s when sending or receiving audio.</span></span> <span data-ttu-id="b49ac-133">閒置時，從 Walkie Talkie 預期的資料使用量不計。</span><span class="sxs-lookup"><span data-stu-id="b49ac-133">When idle, expected data usage from Walkie Talkie is negligible.</span></span>

### <a name="walkie-talkie-devices"></a><span data-ttu-id="b49ac-134">Walkie Talkie 裝置</span><span class="sxs-lookup"><span data-stu-id="b49ac-134">Walkie Talkie devices</span></span>

<span data-ttu-id="b49ac-135">第一線員工工人通常需要朗讀並接收 Walkie Talkie 通話，即使他們的手機已鎖定也一樣。</span><span class="sxs-lookup"><span data-stu-id="b49ac-135">FirstLine workers often need to speak and receive Walkie Talkie calls even when their phones are locked.</span></span> <span data-ttu-id="b49ac-136">透過專用的 PTT 按鈕，就可以使用這種體驗。</span><span class="sxs-lookup"><span data-stu-id="b49ac-136">This experience is possible through specialized devices with a dedicated PTT button.</span></span>

- <span data-ttu-id="b49ac-137">耳機</span><span class="sxs-lookup"><span data-stu-id="b49ac-137">Headsets</span></span>
  - <span data-ttu-id="b49ac-138">有線耳機（[Klein 電子產品](https://www.kleinelectronics.com/poc-accessories/mtwt/)）</span><span class="sxs-lookup"><span data-stu-id="b49ac-138">Wired headsets ([Klein Electronics](https://www.kleinelectronics.com/poc-accessories/mtwt/))</span></span>
  - <span data-ttu-id="b49ac-139">無線耳機（[Jabra BlueParrott](https://www.blueparrott.com/microsoft-teams-walkie-talkie)）</span><span class="sxs-lookup"><span data-stu-id="b49ac-139">Wireless headsets ([Jabra BlueParrott](https://www.blueparrott.com/microsoft-teams-walkie-talkie))</span></span>
- <span data-ttu-id="b49ac-140">耐用手機</span><span class="sxs-lookup"><span data-stu-id="b49ac-140">Rugged phones</span></span>
  - <span data-ttu-id="b49ac-141">Samsung Galaxy XCover Pro</span><span class="sxs-lookup"><span data-stu-id="b49ac-141">Samsung Galaxy XCover Pro</span></span>
    - <span data-ttu-id="b49ac-142">[其他資訊](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/)。</span><span class="sxs-lookup"><span data-stu-id="b49ac-142">[More info](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/).</span></span>
    - <span data-ttu-id="b49ac-143">[安裝指南](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm)。</span><span class="sxs-lookup"><span data-stu-id="b49ac-143">[Setup guide](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm).</span></span>

> [!NOTE]
> <span data-ttu-id="b49ac-144">這些裝置不是經過小組認證。</span><span class="sxs-lookup"><span data-stu-id="b49ac-144">These devices are not Teams certified.</span></span> <span data-ttu-id="b49ac-145">他們已經過驗證，可與團隊 Walkie Talkie 搭配使用。</span><span class="sxs-lookup"><span data-stu-id="b49ac-145">They have been validated to work with Teams Walkie Talkie.</span></span>

### <a name="license-requirements"></a><span data-ttu-id="b49ac-146">授權需求</span><span class="sxs-lookup"><span data-stu-id="b49ac-146">License requirements</span></span>

<span data-ttu-id="b49ac-147">Walkie Talkie 應用程式包含在[Office 365 訂閱](https://docs.microsoft.com/MicrosoftTeams/office-365-licensing)中所有已付費的小組授權中。</span><span class="sxs-lookup"><span data-stu-id="b49ac-147">Walkie Talkie app is included in all paid licenses of Teams in [Office 365 subscriptions](https://docs.microsoft.com/MicrosoftTeams/office-365-licensing).</span></span> <span data-ttu-id="b49ac-148">如需取得團隊的詳細資訊，請參閱 [如何取得 Microsoft 團隊的存取權](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)？</span><span class="sxs-lookup"><span data-stu-id="b49ac-148">For more information about getting Teams, check out [How do I get access to Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)?</span></span>

> [!NOTE]
> <span data-ttu-id="b49ac-149">某些高級功能可能需要額外的授權。</span><span class="sxs-lookup"><span data-stu-id="b49ac-149">Certain advanced features may require additional licensing.</span></span> <span data-ttu-id="b49ac-150">例如，與 Samsung Galaxy XCover Pro 的整合需要 Knox 授權。</span><span class="sxs-lookup"><span data-stu-id="b49ac-150">For example, integration with Samsung Galaxy XCover Pro requires a Knox license.</span></span>

## <a name="further-information"></a><span data-ttu-id="b49ac-151">進一步資訊</span><span class="sxs-lookup"><span data-stu-id="b49ac-151">Further information</span></span>

- <span data-ttu-id="b49ac-152">ITAdmins 可以透過應用程式原則維持對誰使用 Walkie Talkie 的控制權。</span><span class="sxs-lookup"><span data-stu-id="b49ac-152">ITAdmins can maintain control over who is using Walkie Talkie through App Policies.</span></span>
- <span data-ttu-id="b49ac-153">如果您的第一線員工工作者使用行動資料來透過團隊進行通訊，Walkie Talkie 會使用相同的方法。</span><span class="sxs-lookup"><span data-stu-id="b49ac-153">If your firstline worker is using mobile data to communicate via Teams, Walkie Talkie will use the same method.</span></span>
- <span data-ttu-id="b49ac-154">在低頻寬情況下，Walkie Talkie 應該能正常運作，或讓您的智慧型手機連線並正常運作的情況。</span><span class="sxs-lookup"><span data-stu-id="b49ac-154">Walkie Talkie should work well in low bandwidth situations, or situations where your smartphone is connected and working.</span></span> <span data-ttu-id="b49ac-155">如果根本沒有連線，Walkie Talkie 將無法運作。</span><span class="sxs-lookup"><span data-stu-id="b49ac-155">Walkie Talkie will not work when there is no connectivity at all.</span></span>

<span data-ttu-id="b49ac-156">如需有關最終使用者體驗的進一步閱讀，請參閱：</span><span class="sxs-lookup"><span data-stu-id="b49ac-156">For further reading on the end-user experience, see:</span></span>

- [<span data-ttu-id="b49ac-157">開始使用團隊 Walkie Talkie</span><span class="sxs-lookup"><span data-stu-id="b49ac-157">Get started with Teams Walkie Talkie</span></span>](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [<span data-ttu-id="b49ac-158">使用 Walkie Talkie 與您的小組進行溝通</span><span class="sxs-lookup"><span data-stu-id="b49ac-158">Communicate with your team with Walkie Talkie</span></span>](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
