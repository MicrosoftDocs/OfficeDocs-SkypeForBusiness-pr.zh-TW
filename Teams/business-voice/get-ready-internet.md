---
title: 針對 Business Voice 檢查您的網際網路連線
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: ''
appliesto:
- Microsoft Teams
ms.openlocfilehash: 473c053036b766ef475c3aed5f0bba2d24dd9e6c
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824881"
---
# <a name="check-your-internet-connection-for-business-voice"></a><span data-ttu-id="952d6-102">針對 Business Voice 檢查您的網際網路連線</span><span class="sxs-lookup"><span data-stu-id="952d6-102">Check your Internet connection for Business Voice</span></span>

<span data-ttu-id="952d6-103">Business Voice 位於 Microsoft 365 的雲端中。</span><span class="sxs-lookup"><span data-stu-id="952d6-103">Business Voice is located in the cloud with Microsoft 365.</span></span> <span data-ttu-id="952d6-104">使用 Microsoft Teams 和 Business Voice 的每一台裝置都需要連線至網際網路。</span><span class="sxs-lookup"><span data-stu-id="952d6-104">Every device that uses Microsoft Teams and Business Voice needs a connection to the Internet.</span></span>

<span data-ttu-id="952d6-105">若要獲得 Business Voice 的最佳體驗，您需要可支援貴組織每次撥打最多電話數量所需的寬頻網際網路連線。</span><span class="sxs-lookup"><span data-stu-id="952d6-105">To get the best Business Voice experience, you need a broadband Internet connection that can support the maximum number of phone calls that your organization might make at any one time.</span></span> <span data-ttu-id="952d6-106">您也需要確定您網路上的電腦能夠連線至 Microsoft 365 伺服器。</span><span class="sxs-lookup"><span data-stu-id="952d6-106">You also need to make sure that the computers on your network can reach Microsoft 365 servers.</span></span>

<span data-ttu-id="952d6-107">若要執行這些步驟，您必須有具備下列其中一項訂閱的租用戶：</span><span class="sxs-lookup"><span data-stu-id="952d6-107">To follow these steps, you need to have a tenant with one of the following subscriptions:</span></span>

* <span data-ttu-id="952d6-108">Office 365 商務基本版</span><span class="sxs-lookup"><span data-stu-id="952d6-108">Office 365 Business Essentials</span></span>
* <span data-ttu-id="952d6-109">Office 365 商務進階版</span><span class="sxs-lookup"><span data-stu-id="952d6-109">Office 365 Business Premium</span></span>
* <span data-ttu-id="952d6-110">Office 365 E1</span><span class="sxs-lookup"><span data-stu-id="952d6-110">Office 365 E1</span></span>
* <span data-ttu-id="952d6-111">Office 365 E3</span><span class="sxs-lookup"><span data-stu-id="952d6-111">Office 365 E3</span></span>
* <span data-ttu-id="952d6-112">Office 365 F1</span><span class="sxs-lookup"><span data-stu-id="952d6-112">Office 365 F1</span></span>
* <span data-ttu-id="952d6-113">Microsoft 365 A1</span><span class="sxs-lookup"><span data-stu-id="952d6-113">Microsoft 365 A1</span></span>
* <span data-ttu-id="952d6-114">Microsoft 365 A3</span><span class="sxs-lookup"><span data-stu-id="952d6-114">Microsoft 365 A3</span></span>
* <span data-ttu-id="952d6-115">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="952d6-115">Microsoft 365 E3</span></span>
* <span data-ttu-id="952d6-116">Microsoft 365 商務版</span><span class="sxs-lookup"><span data-stu-id="952d6-116">Microsoft 365 Business</span></span>

<span data-ttu-id="952d6-117">您不需要 Business Voice 授權就可以執行這些步驟。</span><span class="sxs-lookup"><span data-stu-id="952d6-117">You don't need a Business Voice license to follow these steps.</span></span>

## <a name="check-your-internet-connection-speed"></a><span data-ttu-id="952d6-118">檢查您的網際網路連線速度</span><span class="sxs-lookup"><span data-stu-id="952d6-118">Check your Internet connection speed</span></span>

<span data-ttu-id="952d6-119">本文可協助判斷您的網際網路連線速度是否足夠因應需要撥打電話和主持視訊會議的人數。</span><span class="sxs-lookup"><span data-stu-id="952d6-119">This article helps determine whether your Internet connection is fast enough for the number of people who need to make phone calls and host video conferences.</span></span> <span data-ttu-id="952d6-120">您將提供關於組織的資訊，並取得顯示 Teams 和 Business Voice 將使用的網際網路連線量的報告。</span><span class="sxs-lookup"><span data-stu-id="952d6-120">You'll provide information about your organization and get back a report that shows how much of your Internet connection will be used by Teams and Business Voice.</span></span>

### <a name="gather-information-about-your-internet-connection-and-users"></a><span data-ttu-id="952d6-121">收集有關您的網際網路連線和使用者的資訊</span><span class="sxs-lookup"><span data-stu-id="952d6-121">Gather information about your Internet connection and users</span></span>

<span data-ttu-id="952d6-122">開始之前，您需要下列資訊：</span><span class="sxs-lookup"><span data-stu-id="952d6-122">Before you start, you need the following information:</span></span>

* <span data-ttu-id="952d6-123">您的網際網路連線速度</span><span class="sxs-lookup"><span data-stu-id="952d6-123">The speed of your Internet connection</span></span>
* <span data-ttu-id="952d6-124">將主要透過您的辦公室使用 Business Voice 的人數</span><span class="sxs-lookup"><span data-stu-id="952d6-124">How many people will use Business Voice mainly from your office</span></span>
* <span data-ttu-id="952d6-125">將主要透過遠端位置 (例如家庭辦公室) 使用 Business Voice 的人數</span><span class="sxs-lookup"><span data-stu-id="952d6-125">How many people will use Business Voice mainly from a remote location, such as a home office</span></span>

### <a name="enter-your-information-into-the-network-planner"></a><span data-ttu-id="952d6-126">將您的資訊輸入網路規劃中心</span><span class="sxs-lookup"><span data-stu-id="952d6-126">Enter your information into the network planner</span></span>

<span data-ttu-id="952d6-127">請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="952d6-127">Follow these steps:</span></span>

1. <span data-ttu-id="952d6-128">在瀏覽器中，移至 https://admin.teams.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="952d6-128">In a browser, go to https://admin.teams.microsoft.com.</span></span> <span data-ttu-id="952d6-129">使用具備全域系統管理員權限的帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="952d6-129">Sign in by using an account that has Global Administrator permissions.</span></span> <span data-ttu-id="952d6-130">您用來註冊 Office 365 的帳戶具備這些權限。</span><span class="sxs-lookup"><span data-stu-id="952d6-130">The account that you used to sign up for Office 365 has these permissions.</span></span>
2. <span data-ttu-id="952d6-131">開啟 **[規劃]**，並選取 **[網路規劃中心]**。</span><span class="sxs-lookup"><span data-stu-id="952d6-131">Open **Planning** and select **Network planner**.</span></span>
3. <span data-ttu-id="952d6-132">在 **[網路規劃]** 底下，選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="952d6-132">Under **Network plans**, select **Add**.</span></span> <span data-ttu-id="952d6-133">為您的規劃輸入名稱，然後選取 **[套用]**。</span><span class="sxs-lookup"><span data-stu-id="952d6-133">Enter a name for your plan, and then select **Apply**.</span></span> <span data-ttu-id="952d6-134">您的網路規劃應看起來如下：</span><span class="sxs-lookup"><span data-stu-id="952d6-134">Your network plan should look like this:</span></span>

    ![網路規劃中心主畫面](../media/network-planner-main.png)
1. <span data-ttu-id="952d6-136">選取網路規劃名稱。</span><span class="sxs-lookup"><span data-stu-id="952d6-136">Select the name of your network plan.</span></span> <span data-ttu-id="952d6-137">(上圖的**總公司**)。</span><span class="sxs-lookup"><span data-stu-id="952d6-137">(It's **Main office** in the preceding picture.)</span></span>
2. <span data-ttu-id="952d6-138">在下一頁，於 **[網站]** 索引標籤底下選取 **[新增網路站台]**。</span><span class="sxs-lookup"><span data-stu-id="952d6-138">On the next page, select **Add a network site** on the **Network sites** tab.</span></span>
3. <span data-ttu-id="952d6-139">只填寫以下螢幕擷取畫面中所指定的欄位，然後選取 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="952d6-139">Fill in only the fields that are indicated in the following screenshot, and then select **Save**.</span></span> <span data-ttu-id="952d6-140">讓這個畫面上的其他欄位保留空白，且不要選取 **[ExpressRoute]** 或 **[連線至 WAN]** 選項。</span><span class="sxs-lookup"><span data-stu-id="952d6-140">Leave the other fields on this screen blank, and don't select the **ExpressRoute** or **Connected to WAN** options.</span></span>

    ![網路規劃中心網站資訊](../media/network-planner-site-info.png)
1. <span data-ttu-id="952d6-142">在 **[報告]** 索引標籤，選取 **[開始報告]**。</span><span class="sxs-lookup"><span data-stu-id="952d6-142">On the **Report** tab, select **Start a report**.</span></span>
1. <span data-ttu-id="952d6-143">輸入下列資訊，然後選取 **[產生報告]**，以建立顯示 Teams 頻寬需求的報告。</span><span class="sxs-lookup"><span data-stu-id="952d6-143">Enter the following information, and then select **Generate report** to create a report that shows the bandwidth requirements for Teams.</span></span> <span data-ttu-id="952d6-144">我們會在下一節中示範如何顯示報告。</span><span class="sxs-lookup"><span data-stu-id="952d6-144">We show you how to read the report in the next section.</span></span>

    ![網路規劃中心報告資訊](../media/network-planner-report-info.png)

### <a name="find-your-minimum-internet-connection-speed"></a><span data-ttu-id="952d6-146">找到您的最低網際網路連線速度</span><span class="sxs-lookup"><span data-stu-id="952d6-146">Find your minimum Internet connection speed</span></span>

<span data-ttu-id="952d6-147">選取 [產生報告]\*\*\*\* 時，Office 365 會建立一個看起來如下的報告：</span><span class="sxs-lookup"><span data-stu-id="952d6-147">When you select **Generate report**, Office 365 creates a report that looks like this:</span></span>

![網路規劃中心報告詳細資料](../media/network-planner-report.png)

<span data-ttu-id="952d6-149">強調顯示的數字會顯示 Teams 和 Business Voice 使用您的網際網路連線量。</span><span class="sxs-lookup"><span data-stu-id="952d6-149">The highlighted number shows how much of your Internet connection Teams and Business Voice will use.</span></span> <span data-ttu-id="952d6-150">建議這個數字不要超過網際網路連線速度總計的 30%。</span><span class="sxs-lookup"><span data-stu-id="952d6-150">We recommend that this number is no more than 30 percent of your total Internet connection speed.</span></span> <span data-ttu-id="952d6-151">例如，如果您的網際網路連線是 60 Mbps，則 Teams 和 Business Voice 不應使用超過 18 Mbps。</span><span class="sxs-lookup"><span data-stu-id="952d6-151">For example, if your Internet connection is 60 Mbps, Teams and Business Voice should use no more than 18 Mbps.</span></span>

<span data-ttu-id="952d6-152">使用此方程式判斷您的最低網際網路連線速度：*\<強調顯示的數字> / 0.3*。</span><span class="sxs-lookup"><span data-stu-id="952d6-152">Use this equation to determine your minimum Internet connection speed: *\<highlighted number> / 0.3*.</span></span> <span data-ttu-id="952d6-153">使用上圖中強調顯示的數字，計算為 *4.6875/0.3 = 15.6*。</span><span class="sxs-lookup"><span data-stu-id="952d6-153">With the number that's highlighted in the preceding image, the calculation is *4.6875 / 0.3 = 15.6*.</span></span> <span data-ttu-id="952d6-154">在此情況下，網際網路連線速度應至少為 15.6 Mbps。</span><span class="sxs-lookup"><span data-stu-id="952d6-154">In this case, the Internet connection speed should be at least 15.6 Mbps.</span></span>

<span data-ttu-id="952d6-155">如果 Teams 和 Business Voice 將使用超過網際網路連線速度總計的 30%，則強調顯示的數字會以紅色顯示。</span><span class="sxs-lookup"><span data-stu-id="952d6-155">If Teams and Business Voice will use more than 30 percent of your total Internet connection speed, the highlighted number will appear red.</span></span> <span data-ttu-id="952d6-156">在這種情況下，您可能需要將網際網路連線升級。</span><span class="sxs-lookup"><span data-stu-id="952d6-156">In that case, you may need to upgrade your Internet connection.</span></span>

![連線速度警告](../media/network-planner-report-speed-warning.png)

## <a name="make-sure-the-computers-and-devices-on-your-network-can-reach-microsoft-365"></a><span data-ttu-id="952d6-158">確定您網路上的電腦和裝置能夠連線至 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="952d6-158">Make sure the computers and devices on your network can reach Microsoft 365</span></span>

<span data-ttu-id="952d6-159">使用 Business Voice 的電腦和裝置必須使用特定網路連接埠與 Microsoft 365 伺服器通訊。</span><span class="sxs-lookup"><span data-stu-id="952d6-159">Computers and devices that use Business Voice must use specific network ports to communicate with Microsoft 365 servers.</span></span> <span data-ttu-id="952d6-160">這些連接埠本質上是門戶，裝置經由它透過網路或網際網路交互通訊。</span><span class="sxs-lookup"><span data-stu-id="952d6-160">These ports are essentially doors through which devices talk to each other over a network or the Internet.</span></span> <span data-ttu-id="952d6-161">您的防火牆需要允許您網路上的裝置透過下列*輸出*網路連接埠來連線至 Microsoft 365：</span><span class="sxs-lookup"><span data-stu-id="952d6-161">Your firewall needs to allow devices on your network to reach Microsoft 365 through the following *outbound* network ports:</span></span>

* <span data-ttu-id="952d6-162">**TCP 連接埠** 80 和 443</span><span class="sxs-lookup"><span data-stu-id="952d6-162">**TCP ports** 80 and 443</span></span>
* <span data-ttu-id="952d6-163">**UDP 連接埠** 3478、3479、3480 和 3481</span><span class="sxs-lookup"><span data-stu-id="952d6-163">**UDP ports** 3478, 3479, 3480, and 3481</span></span>

<span data-ttu-id="952d6-164">檢查您的防火牆是否允許網路連接埠通訊的最簡單方法是在 Teams 中進行測試通話：</span><span class="sxs-lookup"><span data-stu-id="952d6-164">The easiest way to check whether your firewall allows communication on these network ports is to make a test call in Teams:</span></span>

1. <span data-ttu-id="952d6-165">在您網路的電腦上移至 https://aka.ms/getteams，並安裝 Teams。</span><span class="sxs-lookup"><span data-stu-id="952d6-165">Go to https://aka.ms/getteams on a computer on your network and install Teams.</span></span> <span data-ttu-id="952d6-166">確認電腦有喇叭和麥克風。</span><span class="sxs-lookup"><span data-stu-id="952d6-166">Make sure that the computer has speakers and a microphone.</span></span>
2. <span data-ttu-id="952d6-167">使用 Microsoft 365 帳戶開啟 Teams 並登入。</span><span class="sxs-lookup"><span data-stu-id="952d6-167">Open Teams and sign in by using a Microsoft 365 account.</span></span>
3. <span data-ttu-id="952d6-168">在 Teams 中，選取您的個人檔案圖片，然後前往 **[設定]** > **[裝置]**。</span><span class="sxs-lookup"><span data-stu-id="952d6-168">In Teams, select your profile picture, and then go to **Settings** > **Devices**.</span></span>
4. <span data-ttu-id="952d6-169">選擇 **[音訊裝置]** 下的 **[進行測試通話]**。</span><span class="sxs-lookup"><span data-stu-id="952d6-169">Under **Audio devices**, select **Make a test call**.</span></span>
5. <span data-ttu-id="952d6-170">遵循步驟留下訊息並讓訊息向您播放。</span><span class="sxs-lookup"><span data-stu-id="952d6-170">Follow the steps to leave a message and have it played back to you.</span></span>

   * <span data-ttu-id="952d6-171">如果通話可連線，且您聽見訊息，表示防火牆已正確設定。</span><span class="sxs-lookup"><span data-stu-id="952d6-171">If the call connects and you hear your message, your firewall is set up correctly.</span></span>
   * <span data-ttu-id="952d6-172">如果通話可連線，但您無法聽見指示或訊息，請確定您的喇叭和麥克風已正確設定，然後再試一次。</span><span class="sxs-lookup"><span data-stu-id="952d6-172">If the call connects, but you can't hear the instructions or your message, make sure that your speakers and microphone are set up correctly, and then try again.</span></span>
   * <span data-ttu-id="952d6-173">如果通話未連線，或如果通話可連線但您無法聽見訊息，則可能需要更新您的防火牆，以允許存取所需的網路連接埠。</span><span class="sxs-lookup"><span data-stu-id="952d6-173">If the call doesn't connect or it connects but you can't hear your message, you might need to update your firewall to allow access to the required network ports.</span></span> <span data-ttu-id="952d6-174">請參閱您的防火牆文件，或連絡 IT 專家以取得協助。</span><span class="sxs-lookup"><span data-stu-id="952d6-174">Check your firewall's documentation, or contact an IT specialist for help.</span></span>

 <span data-ttu-id="952d6-175">如果您是 IT 專業人員，想要深入了解如何準備更大型或更複雜的網路來支援 Business Voice 的資訊，請參閱[評估我的環境](../3-envision-evaluate-my-environment.md)。</span><span class="sxs-lookup"><span data-stu-id="952d6-175">If you're an IT professional and want more information about how to prepare larger or more complex networks to support Business Voice, see [Evaluate my environment](../3-envision-evaluate-my-environment.md).</span></span> <span data-ttu-id="952d6-176">本文提供關於頻寬、Proxy 和防火牆需求，以及如何使用[網路評估工具](../3-envision-evaluate-my-environment.md#test-the-network)測試網路的更多資訊。</span><span class="sxs-lookup"><span data-stu-id="952d6-176">This article provides information about bandwidth, proxy and firewall requirements, and how to use the [Network Assessment Tool](../3-envision-evaluate-my-environment.md#test-the-network) to test your network.</span></span>

