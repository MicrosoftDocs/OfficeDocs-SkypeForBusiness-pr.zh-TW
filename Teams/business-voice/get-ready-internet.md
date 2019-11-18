---
title: 檢查您的網際網路連線
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: ''
appliesto:
- Microsoft Teams
ms.openlocfilehash: 19f26c0bd7ab4fe89770909d81d60abc97aaa8b0
ms.sourcegitcommit: 4a4ed872eff22663720296ae29c0e644286857f2
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/15/2019
ms.locfileid: "38653549"
---
# <a name="check-your-internet-connection"></a><span data-ttu-id="4b3e5-102">檢查您的網際網路連線</span><span class="sxs-lookup"><span data-stu-id="4b3e5-102">Check your Internet connection</span></span>

<span data-ttu-id="4b3e5-103">Business Voice 位於 Microsoft 365 的雲端中。</span><span class="sxs-lookup"><span data-stu-id="4b3e5-103">Business Voice is located in the cloud with Microsoft 365.</span></span> <span data-ttu-id="4b3e5-104">使用 Microsoft Teams 和 Business Voice 的每一部電腦和裝置都需要連線至網際網路。</span><span class="sxs-lookup"><span data-stu-id="4b3e5-104">Every computer and device that uses Microsoft Teams and Business Voice needs a connection to the Internet.</span></span> <span data-ttu-id="4b3e5-105">若要獲得 Business Voice 的最佳體驗，您需要可支援每次撥打預期的電話數量所需的寬頻網際網路連線。</span><span class="sxs-lookup"><span data-stu-id="4b3e5-105">To get the best experience with Business Voice, you need a broadband Internet connection that can support the expected number of phone calls that will be made at any one time.</span></span> <span data-ttu-id="4b3e5-106">您也需要確定您網路上的電腦能夠連線至 Microsoft 365 伺服器。</span><span class="sxs-lookup"><span data-stu-id="4b3e5-106">You also need to make sure that computers on your network can reach Microsoft 365 servers.</span></span>

<span data-ttu-id="4b3e5-107">若要執行這些步驟，您必須有具備下列其中一項訂閱的租用戶：</span><span class="sxs-lookup"><span data-stu-id="4b3e5-107">To follow these steps, you need to have a tenant with one of the following subscriptions:</span></span>

* <span data-ttu-id="4b3e5-108">Office 365 商務基本版</span><span class="sxs-lookup"><span data-stu-id="4b3e5-108">Office 365 Business Essentials</span></span>
* <span data-ttu-id="4b3e5-109">Office 365 商務進階版</span><span class="sxs-lookup"><span data-stu-id="4b3e5-109">Office 365 Business Premium</span></span>
* <span data-ttu-id="4b3e5-110">Office 365 E1</span><span class="sxs-lookup"><span data-stu-id="4b3e5-110">Office 365 E1</span></span>
* <span data-ttu-id="4b3e5-111">Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="4b3e5-111">Office 365 E3</span></span>
* <span data-ttu-id="4b3e5-112">Office 365 F1</span><span class="sxs-lookup"><span data-stu-id="4b3e5-112">Office 365 F1</span></span>
* <span data-ttu-id="4b3e5-113">Microsoft 365 A1</span><span class="sxs-lookup"><span data-stu-id="4b3e5-113">Microsoft 365 A1</span></span>
* <span data-ttu-id="4b3e5-114">Microsoft 365 A3</span><span class="sxs-lookup"><span data-stu-id="4b3e5-114">Microsoft 365 A3</span></span>
* <span data-ttu-id="4b3e5-115">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="4b3e5-115">Microsoft 365 E3</span></span>
* <span data-ttu-id="4b3e5-116">Microsoft 365 商務版</span><span class="sxs-lookup"><span data-stu-id="4b3e5-116">Microsoft 365 Business</span></span>

<span data-ttu-id="4b3e5-117">您不需要 Business Voice 授權就可以執行這些步驟。</span><span class="sxs-lookup"><span data-stu-id="4b3e5-117">You don't need a Business Voice license to follow these steps.</span></span>

## <a name="check-your-internet-connection-speed"></a><span data-ttu-id="4b3e5-118">檢查您的網際網路連線速度</span><span class="sxs-lookup"><span data-stu-id="4b3e5-118">Check your Internet connection speed</span></span>

<span data-ttu-id="4b3e5-119">本文可協助判斷您的網際網路連線速度，對於撥打電話、主持視訊會議等等所需的人數來說是否足夠快。</span><span class="sxs-lookup"><span data-stu-id="4b3e5-119">This article helps you determine whether your Internet connection is fast enough for the number of people who need to make phone calls, host video conferences, and so on.</span></span> <span data-ttu-id="4b3e5-120">您會輸入一些關於組織的資訊，並取得 Teams 和 Business Voice 將使用您的網際網路連線量的報告。</span><span class="sxs-lookup"><span data-stu-id="4b3e5-120">You'll enter some information about your organization and get back a report with how much of your Internet connection will be used by Teams and Business Voice.</span></span>

### <a name="get-information-about-your-internet-connection-and-users"></a><span data-ttu-id="4b3e5-121">取得有關您的網際網路連線和使用者的資訊</span><span class="sxs-lookup"><span data-stu-id="4b3e5-121">Get information about your Internet connection and users</span></span>

<span data-ttu-id="4b3e5-122">開始之前，您需要知道下列資訊：</span><span class="sxs-lookup"><span data-stu-id="4b3e5-122">Before you start, you need to know the following information:</span></span>

* <span data-ttu-id="4b3e5-123">您的網際網路連線速度。</span><span class="sxs-lookup"><span data-stu-id="4b3e5-123">The speed of your Internet connection.</span></span>
* <span data-ttu-id="4b3e5-124">將主要透過您的辦公室使用 Business Voice 的人數。</span><span class="sxs-lookup"><span data-stu-id="4b3e5-124">How many people will use Business Voice mainly from your office.</span></span>
* <span data-ttu-id="4b3e5-125">將主要透過遠端位置 (例如家庭辦公室) 使用 Business Voice 的人數。</span><span class="sxs-lookup"><span data-stu-id="4b3e5-125">How many people will use Business Voice mainly from a remote location, such as a home office.</span></span>

### <a name="enter-your-information-into-the-network-planner"></a><span data-ttu-id="4b3e5-126">將您的資訊輸入網路規劃中心</span><span class="sxs-lookup"><span data-stu-id="4b3e5-126">Enter your information into the network planner</span></span>

<span data-ttu-id="4b3e5-127">以下是您需要執行的操作：</span><span class="sxs-lookup"><span data-stu-id="4b3e5-127">Here's what you need to do:</span></span>

1. <span data-ttu-id="4b3e5-128">開啟瀏覽器，然後移至 https://admin.teams.microsoft.com，並使用具備全域系統管理員權限的帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="4b3e5-128">Open a browser and go to https://admin.teams.microsoft.com and sign in with an account that has Global Administrator permissions.</span></span> <span data-ttu-id="4b3e5-129">您用來註冊 Office 365 的帳戶具備這些權限。</span><span class="sxs-lookup"><span data-stu-id="4b3e5-129">The account you used to sign up for Office 365 has these permissions.</span></span>
1. <span data-ttu-id="4b3e5-130">開啟 [規劃]\*\*\*\* 然後選取 [網路規劃中心]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4b3e5-130">Open **Org-wide settings** and then select **Network planner**.</span></span>
1. <span data-ttu-id="4b3e5-131">在 [網路規劃]\*\*\*\* 底下，選取 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4b3e5-131">Under **Network plans**, select **Add**.</span></span> <span data-ttu-id="4b3e5-132">為您的規劃命名，然後選取 [套用]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4b3e5-132">Give your plan a name, and then select **Apply**.</span></span> <span data-ttu-id="4b3e5-133">您的網路規劃應看起來如下：</span><span class="sxs-lookup"><span data-stu-id="4b3e5-133">Your network plan should look like this:</span></span>

    ![網路規劃中心主畫面](../media/network-planner-main.png)
1. <span data-ttu-id="4b3e5-135">按一下您的網路規劃名稱 (上圖中的**主辦公室**)。</span><span class="sxs-lookup"><span data-stu-id="4b3e5-135">Click on your network plan's name (**Main office** in the picture above).</span></span>
1. <span data-ttu-id="4b3e5-136">在下一頁上，於 [網站]\*\*\*\* 索引標籤底下選取 [新增網路站台]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4b3e5-136">On the next page, select **Add a network site** under the **Network sites** tab.</span></span>
1. <span data-ttu-id="4b3e5-137">只填寫以下螢幕擷取畫面中所指定的欄位，然後選取 [儲存] \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4b3e5-137">Fill in only the fields indicated in the screenshot below and then select **Save**.</span></span> <span data-ttu-id="4b3e5-138">讓這個畫面上的其他欄位保留空白，且不要選取 [ExpressRoute]\*\*\*\* 或 [連線至 WAN]\*\*\*\* 選項。</span><span class="sxs-lookup"><span data-stu-id="4b3e5-138">Leave the other fields on this screen blank, and don't select either the **ExpressRoute** or **Connected to WAN** options.</span></span>

    ![網路規劃中心網站資訊](../media/network-planner-site-info.png)
1. <span data-ttu-id="4b3e5-140">在 [報告]\*\*\*\* 索引標籤下，選取 [開始報告]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4b3e5-140">Under the **Report** tab, select **Start a report**.</span></span>
1. <span data-ttu-id="4b3e5-141">填寫下列資訊，然後選取 [產生報告]\*\*\*\*，以建立顯示 Teams 頻寬需求的報告。</span><span class="sxs-lookup"><span data-stu-id="4b3e5-141">Fill out the following information and then select **Generate report** to create a report showing the bandwidth requirements for Teams.</span></span> <span data-ttu-id="4b3e5-142">我們會在下一節中示範如何顯示報告。</span><span class="sxs-lookup"><span data-stu-id="4b3e5-142">We'll show you how to read the report in the next section.</span></span>

    ![網路規劃中心報告資訊](../media/network-planner-report-info.png)

### <a name="find-your-minimum-internet-connection-speed"></a><span data-ttu-id="4b3e5-144">找到您的最低網際網路連線速度</span><span class="sxs-lookup"><span data-stu-id="4b3e5-144">Find your minimum Internet connection speed</span></span>

<span data-ttu-id="4b3e5-145">選取 [產生報告]\*\*\*\* 時，Office 365 會建立一個看起來如下的報告：</span><span class="sxs-lookup"><span data-stu-id="4b3e5-145">When you select **Generate report**, Office 365 creates a report that looks like this:</span></span>

![網路規劃中心報告詳細資料](../media/network-planner-report.png)

<span data-ttu-id="4b3e5-147">強調顯示的數字會顯示 Teams 和 Business Voice 使用您的網際網路連線量。</span><span class="sxs-lookup"><span data-stu-id="4b3e5-147">The highlighted number shows how much of your Internet connection Teams and Business Voice will use.</span></span> <span data-ttu-id="4b3e5-148">建議這個數字不要超過網際網路連線速度總計的 30%。</span><span class="sxs-lookup"><span data-stu-id="4b3e5-148">We recommend that this number be no more than 30% of your total Internet connection speed.</span></span> <span data-ttu-id="4b3e5-149">例如，如果您的網際網路連線是60 Mbps，則 Teams 和 Business Voice 不應佔用超過 18 Mbps。</span><span class="sxs-lookup"><span data-stu-id="4b3e5-149">For example, if your Internet connection is 60Mbps, Teams and Business Voice should take up no more than 18Mbps.</span></span>

<span data-ttu-id="4b3e5-150">您可以執行以下計算來找出您的最低網際網路連線速度：`<highlighted number> / .3`。</span><span class="sxs-lookup"><span data-stu-id="4b3e5-150">You can find your minimum Internet connection speed by doing this calculation: `<highlighted number> / .3`.</span></span> <span data-ttu-id="4b3e5-151">使用上圖中強調顯示的數字，此計算會是 `4.6875 / .3 = 15.6`。</span><span class="sxs-lookup"><span data-stu-id="4b3e5-151">Using the highlighted number in the picture above, the calculation would be `4.6875 / .3 = 15.6`.</span></span> <span data-ttu-id="4b3e5-152">這表示您的最低網際網路連線速度必須至少為 15.6 Mbps。</span><span class="sxs-lookup"><span data-stu-id="4b3e5-152">This means your minimum Internet connection speed needs to be at least 15.6Mbps.</span></span>

<span data-ttu-id="4b3e5-153">如果 Teams 和 Business Voice 將使用超過網際網路連線速度總計的 30%，則強調顯示的數字會以紅色顯示。</span><span class="sxs-lookup"><span data-stu-id="4b3e5-153">If Teams and Business Voice will use more than 30% of your total Internet connection speed, the highlighted number will show up as red.</span></span> <span data-ttu-id="4b3e5-154">如果發生這種情況，您可能需要將網際網路連線升級。</span><span class="sxs-lookup"><span data-stu-id="4b3e5-154">If this happens, you might need to upgrade your Internet connection.</span></span>

![連線速度警告](../media/network-planner-report-speed-warning.png)

## <a name="make-sure-computers-and-devices-on-your-network-can-reach-microsoft-365"></a><span data-ttu-id="4b3e5-156">確定您網路上的電腦和裝置能夠連線 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4b3e5-156">Make sure computers and devices on your network can reach Microsoft 365</span></span>

<span data-ttu-id="4b3e5-157">若要正常運作，您要搭配 Business Voice 使用的電腦和裝置必須使用特定網路連接埠與 Microsoft 365 伺服器通訊。</span><span class="sxs-lookup"><span data-stu-id="4b3e5-157">To work correctly, computers and devices you want to use with Business Voice need to communicate with Microsoft 365 servers using specific network ports.</span></span> <span data-ttu-id="4b3e5-158">網路連接埠本質上是門戶，電腦和裝置可以經由它透過網路或網際網路彼此交談。</span><span class="sxs-lookup"><span data-stu-id="4b3e5-158">Network ports are essentially doors through which computers and devices can talk to each other over a network or the Internet.</span></span> <span data-ttu-id="4b3e5-159">您的防火牆需要允許您網路上的電腦和裝置能夠使用下列輸出網路連接埠來連線 Microsoft 365：</span><span class="sxs-lookup"><span data-stu-id="4b3e5-159">Your firewall needs to allow computers and devices on your network to reach Microsoft 365 using the following outbound network ports:</span></span>

* <span data-ttu-id="4b3e5-160">**TCP 連接埠** 80 和 443</span><span class="sxs-lookup"><span data-stu-id="4b3e5-160">**TCP ports** 80 and 443</span></span>
* <span data-ttu-id="4b3e5-161">**UDP 連接埠** 3478、3479、3480 和 3481</span><span class="sxs-lookup"><span data-stu-id="4b3e5-161">**UDP ports** 3478, 3479, 3480, and 3481</span></span>

<span data-ttu-id="4b3e5-162">檢查您的防火牆是否允許網路連接埠通訊的最簡單方法是使用 Teams 進行測試通話。</span><span class="sxs-lookup"><span data-stu-id="4b3e5-162">The easiest way to check whether your firewall allows communication on these network ports is to make a test call using Teams.</span></span> <span data-ttu-id="4b3e5-163">若要進行測試通話，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="4b3e5-163">To make a test call, do the following:</span></span>

1. <span data-ttu-id="4b3e5-164">在您網路的電腦上移至 https://aka.ms/getteams，以安裝 Teams。</span><span class="sxs-lookup"><span data-stu-id="4b3e5-164">Go to https://aka.ms/getteams on a computer on your network to install Teams.</span></span> <span data-ttu-id="4b3e5-165">確定喇叭和麥克風已連線至此電腦。</span><span class="sxs-lookup"><span data-stu-id="4b3e5-165">Make sure speakers and a microphone are connected to this computer.</span></span>
2. <span data-ttu-id="4b3e5-166">使用 Microsoft 365 帳戶開啟 Teams 並登入</span><span class="sxs-lookup"><span data-stu-id="4b3e5-166">Open Teams and sign in using a Microsoft 365 account</span></span>
3. <span data-ttu-id="4b3e5-167">在 Teams 中，選取您的個人檔案圖片，然後選取 [設定]\*\*\*\*  >  [裝置]\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="4b3e5-167">In Teams, select your profile picture, then **Settings** > **Devices**</span></span>
4. <span data-ttu-id="4b3e5-168">選擇 [音訊裝置]\*\*\*\* 下的 [音訊裝置]\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="4b3e5-168">Choose **Make a test call** under **Audio devices**</span></span>
5. <span data-ttu-id="4b3e5-169">遵循提示留下訊息並讓訊息向您播放</span><span class="sxs-lookup"><span data-stu-id="4b3e5-169">Follow the prompts to leave a message and have it played back to you</span></span>

* <span data-ttu-id="4b3e5-170">如果通話可連線，且您可以聽見您的訊息向您播放，您的防火牆即已正確設定。</span><span class="sxs-lookup"><span data-stu-id="4b3e5-170">If the call connects and you can hear your message played back to you, your firewall is set up correctly.</span></span>
* <span data-ttu-id="4b3e5-171">如果通話可連線，但您無法聽見提示或聽見您的訊息向您播放，請確定您的喇叭和麥克風已正確設定，且電腦可以偵測到。</span><span class="sxs-lookup"><span data-stu-id="4b3e5-171">If the call connects but you can't hear the prompts or your message played back to you, make sure your speakers and microphone are set up correctly and detected by the computer.</span></span> <span data-ttu-id="4b3e5-172">請再試一次。</span><span class="sxs-lookup"><span data-stu-id="4b3e5-172">Try again.</span></span>
* <span data-ttu-id="4b3e5-173">如果通話未連線，或如果通話可連線但您無法聽見您的訊息向您播放，則可能需要更新您的防火牆，以允許以上所列的網路連接埠。</span><span class="sxs-lookup"><span data-stu-id="4b3e5-173">If the call doesn't connect or if it does but you can't hear your message played back to you, you might need to update your firewall to allow the network ports listed above.</span></span> <span data-ttu-id="4b3e5-174">查看您的防火牆文件，了解如何允許網路連接埠連線網際網路，或與 IT 專家連絡以協助您。</span><span class="sxs-lookup"><span data-stu-id="4b3e5-174">Check your firewall's documentation on how to allow network ports to reach the Internet, or contact an IT specialist to help you.</span></span>

<span data-ttu-id="4b3e5-175">如果您是 IT 專業人員，想要深入了解如何準備更大型或更複雜的網路來支援 Business Voice 的資訊，請參閱[評估我的環境](../3-envision-evaluate-my-environment.md)。</span><span class="sxs-lookup"><span data-stu-id="4b3e5-175">If you're an IT professional and want more information about how to prepare larger or more complex networks to support Business Voice, take a look at [Evaluate my environment](../3-envision-evaluate-my-environment.md).</span></span> <span data-ttu-id="4b3e5-176">[評估我的環境](../3-envision-evaluate-my-environment.md)文章提供關於頻寬、Proxy 和防火牆需求，以及如何使用[網路評估工具](../3-envision-evaluate-my-environment.md#test-the-network)測試網路的更多資訊。</span><span class="sxs-lookup"><span data-stu-id="4b3e5-176">The [Evaluate my environment](../3-envision-evaluate-my-environment.md) article gives additional information about bandwidth, proxy, and firewall requirements and also how to test your network using the [Network Assessment Tool](../3-envision-evaluate-my-environment.md#test-the-network).</span></span>
