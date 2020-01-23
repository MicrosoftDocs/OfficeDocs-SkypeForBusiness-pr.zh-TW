---
title: 針對 Business Voice 檢查您的網際網路連線
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
ms.openlocfilehash: 17eca42d01bcfb8a6b440c16408f31f6301b0338
ms.sourcegitcommit: 9bead87a7f4c4e71f19f8980e9dce2b979735055
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/23/2020
ms.locfileid: "41268709"
---
# <a name="check-your-internet-connection-for-business-voice"></a><span data-ttu-id="b4dfb-102">針對 Business Voice 檢查您的網際網路連線</span><span class="sxs-lookup"><span data-stu-id="b4dfb-102">Check your Internet connection for Business Voice</span></span>

<span data-ttu-id="b4dfb-103">Business Voice 位於 Microsoft 365 的雲端中。</span><span class="sxs-lookup"><span data-stu-id="b4dfb-103">Business Voice is located in the cloud with Microsoft 365.</span></span> <span data-ttu-id="b4dfb-104">使用 Microsoft Teams 和 Business Voice 的每一台裝置都需要連線至網際網路。</span><span class="sxs-lookup"><span data-stu-id="b4dfb-104">Every computer and device that uses Microsoft Teams and Business Voice needs a connection to the Internet.</span></span>

<span data-ttu-id="b4dfb-105">若要獲得 Business Voice 的最佳體驗，您需要可支援貴組織每次撥打最多電話數量所需的寬頻網際網路連線。</span><span class="sxs-lookup"><span data-stu-id="b4dfb-105">To get the best experience with Business Voice, you need a broadband Internet connection that can support the expected number of phone calls that will be made at any one time.</span></span> <span data-ttu-id="b4dfb-106">您也需要確定您網路上的電腦能夠連線至 Microsoft 365 伺服器。</span><span class="sxs-lookup"><span data-stu-id="b4dfb-106">You also need to make sure that computers on your network can reach Microsoft 365 servers.</span></span>

<span data-ttu-id="b4dfb-107">若要執行這些步驟，您必須有具備下列其中一項訂閱的租用戶：</span><span class="sxs-lookup"><span data-stu-id="b4dfb-107">To follow these steps, you need to have a tenant with one of the following subscriptions:</span></span>

* <span data-ttu-id="b4dfb-108">Office 365 商務基本版</span><span class="sxs-lookup"><span data-stu-id="b4dfb-108">Office 365 Business Essentials</span></span>
* <span data-ttu-id="b4dfb-109">Office 365 商務進階版</span><span class="sxs-lookup"><span data-stu-id="b4dfb-109">Office 365 Business Premium</span></span>
* <span data-ttu-id="b4dfb-110">Office 365 E1</span><span class="sxs-lookup"><span data-stu-id="b4dfb-110">Office 365 E1</span></span>
* <span data-ttu-id="b4dfb-111">Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="b4dfb-111">Office 365 E3</span></span>
* <span data-ttu-id="b4dfb-112">Office 365 F1</span><span class="sxs-lookup"><span data-stu-id="b4dfb-112">Office 365 F1</span></span>
* <span data-ttu-id="b4dfb-113">Microsoft 365 A1</span><span class="sxs-lookup"><span data-stu-id="b4dfb-113">Microsoft 365 A1</span></span>
* <span data-ttu-id="b4dfb-114">Microsoft 365 A3</span><span class="sxs-lookup"><span data-stu-id="b4dfb-114">Microsoft 365 A3</span></span>
* <span data-ttu-id="b4dfb-115">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="b4dfb-115">Microsoft 365 E3</span></span>
* <span data-ttu-id="b4dfb-116">Microsoft 365 商務版</span><span class="sxs-lookup"><span data-stu-id="b4dfb-116">Microsoft 365 Business</span></span>

<span data-ttu-id="b4dfb-117">您不需要 Business Voice 授權就可以執行這些步驟。</span><span class="sxs-lookup"><span data-stu-id="b4dfb-117">You don't need a Business Voice license to follow these steps.</span></span>

## <a name="check-your-internet-connection-speed"></a><span data-ttu-id="b4dfb-118">檢查您的網際網路連線速度</span><span class="sxs-lookup"><span data-stu-id="b4dfb-118">Check your Internet connection speed</span></span>

<span data-ttu-id="b4dfb-119">本文可協助判斷您的網際網路連線速度是否足夠因應需要撥打電話和主持視訊會議的人數。</span><span class="sxs-lookup"><span data-stu-id="b4dfb-119">This article helps you determine whether your Internet connection is fast enough for the number of people who need to make phone calls, host video conferences, and so on.</span></span> <span data-ttu-id="b4dfb-120">您將提供關於組織的資訊，並取得顯示 Teams 和 Business Voice 將使用的網際網路連線量的報告。</span><span class="sxs-lookup"><span data-stu-id="b4dfb-120">You'll enter some information about your organization and get back a report with how much of your Internet connection will be used by Teams and Business Voice.</span></span>

### <a name="gather-information-about-your-internet-connection-and-users"></a><span data-ttu-id="b4dfb-121">收集有關您的網際網路連線和使用者的資訊</span><span class="sxs-lookup"><span data-stu-id="b4dfb-121">Get information about your Internet connection and users</span></span>

<span data-ttu-id="b4dfb-122">開始之前，您需要下列資訊：</span><span class="sxs-lookup"><span data-stu-id="b4dfb-122">Before you start, you need to know the following information:</span></span>

* <span data-ttu-id="b4dfb-123">您的網際網路連線速度</span><span class="sxs-lookup"><span data-stu-id="b4dfb-123">The speed of your Internet connection.</span></span>
* <span data-ttu-id="b4dfb-124">將主要透過您的辦公室使用 Business Voice 的人數</span><span class="sxs-lookup"><span data-stu-id="b4dfb-124">How many people will use Business Voice mainly from your office.</span></span>
* <span data-ttu-id="b4dfb-125">將主要透過遠端位置 (例如家庭辦公室) 使用 Business Voice 的人數</span><span class="sxs-lookup"><span data-stu-id="b4dfb-125">How many people will use Business Voice mainly from a remote location, such as a home office.</span></span>

### <a name="enter-your-information-into-the-network-planner"></a><span data-ttu-id="b4dfb-126">將您的資訊輸入網路規劃中心</span><span class="sxs-lookup"><span data-stu-id="b4dfb-126">Enter your information into the network planner</span></span>

<span data-ttu-id="b4dfb-127">請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="b4dfb-127">Follow these steps:</span></span>

1. <span data-ttu-id="b4dfb-128">在瀏覽器中，移至 https://admin.teams.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="b4dfb-128">In a browser, go to https://admin.teams.microsoft.com.</span></span> <span data-ttu-id="b4dfb-129">使用具備全域系統管理員權限的帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="b4dfb-129">Sign in by using an account that has Global Administrator permissions.</span></span> <span data-ttu-id="b4dfb-130">您用來註冊 Office 365 的帳戶具備這些權限。</span><span class="sxs-lookup"><span data-stu-id="b4dfb-130">The account you used to sign up for Office 365 has these permissions.</span></span>
2. <span data-ttu-id="b4dfb-131">開啟 **[規劃]**，並選取 **[網路規劃中心]**。</span><span class="sxs-lookup"><span data-stu-id="b4dfb-131">Open **Planning** and then select **Network planner**.</span></span>
3. <span data-ttu-id="b4dfb-132">在 **[網路規劃]** 底下，選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="b4dfb-132">Under **Network plans**, select **Add**.</span></span> <span data-ttu-id="b4dfb-133">為您的規劃輸入名稱，然後選取 **[套用]**。</span><span class="sxs-lookup"><span data-stu-id="b4dfb-133">Enter a name for your plan, and then select **Apply**.</span></span> <span data-ttu-id="b4dfb-134">您的網路規劃應看起來如下：</span><span class="sxs-lookup"><span data-stu-id="b4dfb-134">Your network plan should look like this:</span></span>

    ![網路規劃中心主畫面](../media/network-planner-main.png)
1. <span data-ttu-id="b4dfb-136">選取網路規劃名稱。</span><span class="sxs-lookup"><span data-stu-id="b4dfb-136">Select the name of your network plan.</span></span> <span data-ttu-id="b4dfb-137">(上圖的**總公司**)。</span><span class="sxs-lookup"><span data-stu-id="b4dfb-137">(It's **Main office** in the preceding picture.)</span></span>
2. <span data-ttu-id="b4dfb-138">在下一頁，於 **[網站]** 索引標籤底下選取 **[新增網路站台]**。</span><span class="sxs-lookup"><span data-stu-id="b4dfb-138">On the next page, select **Add a network site** under the **Network sites** tab.</span></span>
3. <span data-ttu-id="b4dfb-139">只填寫以下螢幕擷取畫面中所指定的欄位，然後選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="b4dfb-139">Fill in only the fields indicated in the screenshot below and then select **Save**.</span></span> <span data-ttu-id="b4dfb-140">讓這個畫面上的其他欄位保留空白，且不要選取 **[ExpressRoute]** 或 **[連線至 WAN]** 選項。</span><span class="sxs-lookup"><span data-stu-id="b4dfb-140">Leave the other fields on this screen blank, and don't select either the **ExpressRoute** or **Connected to WAN** options.</span></span>

    ![網路規劃中心網站資訊](../media/network-planner-site-info.png)
1. <span data-ttu-id="b4dfb-142">在 **[報告]** 索引標籤，選取 **[開始報告]**。</span><span class="sxs-lookup"><span data-stu-id="b4dfb-142">Under the **Report** tab, select **Start a report**.</span></span>
1. <span data-ttu-id="b4dfb-143">輸入下列資訊，然後選取 **[產生報告]**，以建立顯示 Teams 頻寬需求的報告。</span><span class="sxs-lookup"><span data-stu-id="b4dfb-143">Fill out the following information and then select **Generate report** to create a report showing the bandwidth requirements for Teams.</span></span> <span data-ttu-id="b4dfb-144">我們會在下一節中示範如何顯示報告。</span><span class="sxs-lookup"><span data-stu-id="b4dfb-144">We'll show you how to read the report in the next section.</span></span>

    ![網路規劃中心報告資訊](../media/network-planner-report-info.png)

### <a name="find-your-minimum-internet-connection-speed"></a><span data-ttu-id="b4dfb-146">找到您的最低網際網路連線速度</span><span class="sxs-lookup"><span data-stu-id="b4dfb-146">Find your minimum Internet connection speed</span></span>

<span data-ttu-id="b4dfb-147">選取 [產生報告]\*\*\*\* 時，Office 365 會建立一個看起來如下的報告：</span><span class="sxs-lookup"><span data-stu-id="b4dfb-147">When you select **Generate report**, Office 365 creates a report that looks like this:</span></span>

![網路規劃中心報告詳細資料](../media/network-planner-report.png)

<span data-ttu-id="b4dfb-149">強調顯示的數字會顯示 Teams 和 Business Voice 使用您的網際網路連線量。</span><span class="sxs-lookup"><span data-stu-id="b4dfb-149">The highlighted number shows how much of your Internet connection Teams and Business Voice will use.</span></span> <span data-ttu-id="b4dfb-150">建議這個數字不要超過網際網路連線速度總計的 30%。</span><span class="sxs-lookup"><span data-stu-id="b4dfb-150">We recommend that this number be no more than 30% of your total Internet connection speed.</span></span> <span data-ttu-id="b4dfb-151">例如，如果您的網際網路連線是 60 Mbps，則 Teams 和 Business Voice 不應使用超過 18 Mbps。</span><span class="sxs-lookup"><span data-stu-id="b4dfb-151">For example, if your Internet connection is 60Mbps, Teams and Business Voice should take up no more than 18Mbps.</span></span>

<span data-ttu-id="b4dfb-152">使用此方程式判斷您的最低網際網路連線速度：*\<強調顯示的數字> / 0.3*。</span><span class="sxs-lookup"><span data-stu-id="b4dfb-152">Use this equation to determine your minimum Internet connection speed: *\<highlighted number> / 0.3*.</span></span> <span data-ttu-id="b4dfb-153">使用上圖中強調顯示的數字，計算為 *4.6875/0.3 = 15.6*。</span><span class="sxs-lookup"><span data-stu-id="b4dfb-153">With the number that's highlighted in the preceding image, the calculation is *4.6875 / 0.3 = 15.6*.</span></span> <span data-ttu-id="b4dfb-154">在此情況下，網際網路連線速度應至少為 15.6 Mbps。</span><span class="sxs-lookup"><span data-stu-id="b4dfb-154">In this case, the Internet connection speed should be at least 15.6 Mbps.</span></span>

<span data-ttu-id="b4dfb-155">如果 Teams 和 Business Voice 將使用超過網際網路連線速度總計的 30%，則強調顯示的數字會以紅色顯示。</span><span class="sxs-lookup"><span data-stu-id="b4dfb-155">If Teams and Business Voice will use more than 30% of your total Internet connection speed, the highlighted number will show up as red.</span></span> <span data-ttu-id="b4dfb-156">在這種情況下，您可能需要將網際網路連線升級。</span><span class="sxs-lookup"><span data-stu-id="b4dfb-156">In that case, you may need to upgrade your Internet connection.</span></span>

![連線速度警告](../media/network-planner-report-speed-warning.png)

## <a name="make-sure-the-computers-and-devices-on-your-network-can-reach-microsoft-365"></a><span data-ttu-id="b4dfb-158">確定您網路上的電腦和裝置能夠連線至 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b4dfb-158">Make sure computers and devices on your network can reach Microsoft 365</span></span>

<span data-ttu-id="b4dfb-159">使用 Business Voice 的電腦和裝置必須使用特定網路連接埠與 Microsoft 365 伺服器通訊。</span><span class="sxs-lookup"><span data-stu-id="b4dfb-159">Computers and devices that use Business Voice must use specific network ports to communicate with Microsoft 365 servers.</span></span> <span data-ttu-id="b4dfb-160">這些連接埠本質上是門戶，裝置經由它透過網路或網際網路交互通訊。</span><span class="sxs-lookup"><span data-stu-id="b4dfb-160">Network ports are essentially doors through which computers and devices can talk to each other over a network or the Internet.</span></span> <span data-ttu-id="b4dfb-161">您的防火牆需要允許您網路上的裝置透過下列*輸出*網路連接埠來連線至 Microsoft 365：</span><span class="sxs-lookup"><span data-stu-id="b4dfb-161">Your firewall needs to allow computers and devices on your network to reach Microsoft 365 using the following outbound network ports:</span></span>

* <span data-ttu-id="b4dfb-162">**TCP 連接埠** 80 和 443</span><span class="sxs-lookup"><span data-stu-id="b4dfb-162">**TCP ports** 80 and 443</span></span>
* <span data-ttu-id="b4dfb-163">**UDP 連接埠** 3478、3479、3480 和 3481</span><span class="sxs-lookup"><span data-stu-id="b4dfb-163">**UDP ports** 3478, 3479, 3480, and 3481</span></span>

<span data-ttu-id="b4dfb-164">檢查您的防火牆是否允許網路連接埠通訊的最簡單方法是在 Teams 中進行測試通話：</span><span class="sxs-lookup"><span data-stu-id="b4dfb-164">The easiest way to check whether your firewall allows communication on these network ports is to make a test call using Teams.</span></span>

1. <span data-ttu-id="b4dfb-165">在您網路的電腦上移至 https://aka.ms/getteams，並安裝 Teams。</span><span class="sxs-lookup"><span data-stu-id="b4dfb-165">Go to https://aka.ms/getteams on a computer on your network to install Teams.</span></span> <span data-ttu-id="b4dfb-166">確認電腦有喇叭和麥克風。</span><span class="sxs-lookup"><span data-stu-id="b4dfb-166">Make sure that the computer has speakers and a microphone.</span></span>
2. <span data-ttu-id="b4dfb-167">使用 Microsoft 365 帳戶開啟 Teams 並登入。</span><span class="sxs-lookup"><span data-stu-id="b4dfb-167">Open Teams and sign in using a Microsoft 365 account</span></span>
3. <span data-ttu-id="b4dfb-168">在 Teams 中，選取您的個人檔案圖片，然後前往 **[設定]** > **[裝置]**。</span><span class="sxs-lookup"><span data-stu-id="b4dfb-168">In Teams, select your profile picture, then **Settings** > **Devices**</span></span>
4. <span data-ttu-id="b4dfb-169">選擇 **[音訊裝置]** 下的 **[進行測試通話]**。</span><span class="sxs-lookup"><span data-stu-id="b4dfb-169">Under **Audio devices**, select **Make a test call**.</span></span>
5. <span data-ttu-id="b4dfb-170">遵循步驟留下訊息並讓訊息向您播放。</span><span class="sxs-lookup"><span data-stu-id="b4dfb-170">Follow the prompts to leave a message and have it played back to you</span></span>

   * <span data-ttu-id="b4dfb-171">如果通話可連線，且您聽見訊息，表示防火牆已正確設定。</span><span class="sxs-lookup"><span data-stu-id="b4dfb-171">If the call connects and you can hear your message played back to you, your firewall is set up correctly.</span></span>
   * <span data-ttu-id="b4dfb-172">如果通話可連線，但您無法聽見指示或訊息，請確定您的喇叭和麥克風已正確設定，然後再試一次。</span><span class="sxs-lookup"><span data-stu-id="b4dfb-172">If the call connects but you can't hear the prompts or your message played back to you, make sure your speakers and microphone are set up correctly and detected by the computer.</span></span>
   * <span data-ttu-id="b4dfb-173">如果通話未連線，或如果通話可連線但您無法聽見訊息，則可能需要更新您的防火牆，以允許存取所需的網路連接埠。</span><span class="sxs-lookup"><span data-stu-id="b4dfb-173">If the call doesn't connect or if it does but you can't hear your message played back to you, you might need to update your firewall to allow the network ports listed above.</span></span> <span data-ttu-id="b4dfb-174">請參閱您的防火牆文件，或連絡 IT 專家以取得協助。</span><span class="sxs-lookup"><span data-stu-id="b4dfb-174">Check your firewall's documentation, or contact an IT specialist for help.</span></span>

 <span data-ttu-id="b4dfb-175">如果您是 IT 專業人員，想要深入了解如何準備更大型或更複雜的網路來支援 Business Voice 的資訊，請參閱[評估我的環境](../3-envision-evaluate-my-environment.md)。</span><span class="sxs-lookup"><span data-stu-id="b4dfb-175">If you're an IT professional and want more information about how to prepare larger or more complex networks to support Business Voice, take a look at [Evaluate my environment](../3-envision-evaluate-my-environment.md).</span></span> <span data-ttu-id="b4dfb-176">本文提供關於頻寬、Proxy 和防火牆需求，以及如何使用[網路評估工具](../3-envision-evaluate-my-environment.md#test-the-network)測試網路的更多資訊。</span><span class="sxs-lookup"><span data-stu-id="b4dfb-176">This article provides information about bandwidth, proxy and firewall requirements, and how to use the [Network Assessment Tool](../3-envision-evaluate-my-environment.md#test-the-network) to test your network.</span></span>

