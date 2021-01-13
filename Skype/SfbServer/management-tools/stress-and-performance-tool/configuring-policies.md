---
title: 設定商務用 Skype Server 2015 應力和效能工具的原則
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 11/11/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7e1435e2-d073-4265-8067-ebcb5bf28835
description: 商務用 Skype Server 2015 應力和效能工具的原則設定。
ms.openlocfilehash: bb049d5740d74e5ebeacd8a21d00e2644da61a7c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815033"
---
# <a name="configuring-policies-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="de9f2-103">設定商務用 Skype Server 2015 應力和效能工具的原則</span><span class="sxs-lookup"><span data-stu-id="de9f2-103">Configuring policies for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="de9f2-104">商務用 Skype Server 2015 應力和效能工具的原則設定。</span><span class="sxs-lookup"><span data-stu-id="de9f2-104">Policy configuration for Skype for Business Server 2015 Stress and Performance Tool.</span></span>
  
<span data-ttu-id="de9f2-105">在執行壓力和效能工具之前，您可以在商務用 Skype Server 2015 中設定數個原則及其他區域：</span><span class="sxs-lookup"><span data-stu-id="de9f2-105">There are several policies and other areas that you can configure in Skype for Business Server 2015, prior to running the Stress and Performance Tool:</span></span>
  
- [<span data-ttu-id="de9f2-106">封存原則</span><span class="sxs-lookup"><span data-stu-id="de9f2-106">Archiving policy</span></span>](configuring-policies.md#ArchivingPolicy)
    
- [<span data-ttu-id="de9f2-107">會議原則</span><span class="sxs-lookup"><span data-stu-id="de9f2-107">Conferencing policy</span></span>](configuring-policies.md#ConferencingPolicy)
    
- [<span data-ttu-id="de9f2-108">連絡人原則</span><span class="sxs-lookup"><span data-stu-id="de9f2-108">Contacts policy</span></span>](configuring-policies.md#ContactsPolicy)
    
- [<span data-ttu-id="de9f2-109">同盟原則</span><span class="sxs-lookup"><span data-stu-id="de9f2-109">Federation policy</span></span>](configuring-policies.md#FederationPolicy)
    
- [<span data-ttu-id="de9f2-110">通話許可控制原則</span><span class="sxs-lookup"><span data-stu-id="de9f2-110">Call Admission Control policy</span></span>](configuring-policies.md#CACPolicy)
    
- [<span data-ttu-id="de9f2-111">語音路由規則</span><span class="sxs-lookup"><span data-stu-id="de9f2-111">Voice Routing rules</span></span>](configuring-policies.md#VoiceRoutingRules)
    
- [<span data-ttu-id="de9f2-112">會議助理應用程式</span><span class="sxs-lookup"><span data-stu-id="de9f2-112">Conference Attendant application</span></span>](configuring-policies.md#ConfAttendantApp)
    
- [<span data-ttu-id="de9f2-113">伺服器呼叫駐留服務</span><span class="sxs-lookup"><span data-stu-id="de9f2-113">Server Call Park service</span></span>](configuring-policies.md#ServerCallParkServ)
    
- [<span data-ttu-id="de9f2-114">緊急通話</span><span class="sxs-lookup"><span data-stu-id="de9f2-114">Emergency calls</span></span>](configuring-policies.md#EmergencyCalls)
    
- [<span data-ttu-id="de9f2-115">設定回應群組應用程式</span><span class="sxs-lookup"><span data-stu-id="de9f2-115">Configuring Response Group application</span></span>](configuring-policies.md#ConfigResponseGroupApp)
    
## <a name="archiving-policy"></a><span data-ttu-id="de9f2-116">封存原則</span><span class="sxs-lookup"><span data-stu-id="de9f2-116">Archiving policy</span></span>
<span data-ttu-id="de9f2-117"><a name="ArchivingPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="de9f2-117"><a name="ArchivingPolicy"> </a></span></span>

<span data-ttu-id="de9f2-118">如果您已在商務用 Skype Server 拓撲中部署封存伺服器，則可以查看 ArchivingPolicy.ps1 腳本。</span><span class="sxs-lookup"><span data-stu-id="de9f2-118">If you have an Archiving server deployed in your Skype for Business Server topology, you can look at the ArchivingPolicy.ps1 script.</span></span> <span data-ttu-id="de9f2-119">如果您需要進一步協助，請參閱封存和 Web 會議 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="de9f2-119">If you need further assistance, check out the Archiving and Web Conferencing cmdlets.</span></span>
  
## <a name="conferencing-policy"></a><span data-ttu-id="de9f2-120">會議原則</span><span class="sxs-lookup"><span data-stu-id="de9f2-120">Conferencing policy</span></span>
<span data-ttu-id="de9f2-121"><a name="ConferencingPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="de9f2-121"><a name="ConferencingPolicy"> </a></span></span>

<span data-ttu-id="de9f2-122">若為會議，我們有 MeetingPolicy.ps1 腳本。</span><span class="sxs-lookup"><span data-stu-id="de9f2-122">For conferencing, we have the MeetingPolicy.ps1 script.</span></span> <span data-ttu-id="de9f2-123">如果您需要進一步協助，請參閱 Web 會議 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="de9f2-123">If you need further assistance, check out the Web Conferencing cmdlets.</span></span>
  
## <a name="contacts-policy"></a><span data-ttu-id="de9f2-124">連絡人原則</span><span class="sxs-lookup"><span data-stu-id="de9f2-124">Contacts policy</span></span>
<span data-ttu-id="de9f2-125"><a name="ContactsPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="de9f2-125"><a name="ContactsPolicy"> </a></span></span>

<span data-ttu-id="de9f2-126">ContactsPolicy.ps1 腳本將會是您需要複習的範例。</span><span class="sxs-lookup"><span data-stu-id="de9f2-126">ContactsPolicy.ps1 script will be the sample you'll need to review.</span></span> <span data-ttu-id="de9f2-127">如果您需要進一步參考，IM 和目前狀態 Cmdlet 會有所説明。</span><span class="sxs-lookup"><span data-stu-id="de9f2-127">The IM and Presence cmdlets will help if you need further references.</span></span>
  
## <a name="federation-policy"></a><span data-ttu-id="de9f2-128">同盟原則</span><span class="sxs-lookup"><span data-stu-id="de9f2-128">Federation policy</span></span>
<span data-ttu-id="de9f2-129"><a name="FederationPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="de9f2-129"><a name="FederationPolicy"> </a></span></span>

<span data-ttu-id="de9f2-130">同盟的範例腳本是 FederationPolicy.ps1。</span><span class="sxs-lookup"><span data-stu-id="de9f2-130">The sample script for federation is FederationPolicy.ps1.</span></span> <span data-ttu-id="de9f2-131">若您需要深入瞭解，請複查 Cmdlet，將會是 Edge Server、同盟和外部存取。</span><span class="sxs-lookup"><span data-stu-id="de9f2-131">The cmdlets to review, if you need further insight, will be Edge Server, federation, and external access.</span></span>
  
## <a name="call-admission-control-policy"></a><span data-ttu-id="de9f2-132">通話許可控制原則</span><span class="sxs-lookup"><span data-stu-id="de9f2-132">Call Admission Control policy</span></span>
<span data-ttu-id="de9f2-133"><a name="CACPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="de9f2-133"><a name="CACPolicy"> </a></span></span>

<span data-ttu-id="de9f2-134">您可以參照此原則的 BandwidthPolicy.ps1。</span><span class="sxs-lookup"><span data-stu-id="de9f2-134">You can reference BandwidthPolicy.ps1 for this policy.</span></span> <span data-ttu-id="de9f2-135">通話許可控制 Cmdlet 也會有進一步的資訊。</span><span class="sxs-lookup"><span data-stu-id="de9f2-135">The Call Admission Control cmdlets will have further information as well.</span></span>
  
## <a name="voice-routing-rules"></a><span data-ttu-id="de9f2-136">語音路由規則</span><span class="sxs-lookup"><span data-stu-id="de9f2-136">Voice Routing rules</span></span>
<span data-ttu-id="de9f2-137"><a name="VoiceRoutingRules"> </a></span><span class="sxs-lookup"><span data-stu-id="de9f2-137"><a name="VoiceRoutingRules"> </a></span></span>

<span data-ttu-id="de9f2-138">您需要語音路由的 RoutingRules.ps1 範例腳本。</span><span class="sxs-lookup"><span data-stu-id="de9f2-138">You'll need the RoutingRules.ps1 sample script for Voice Routing.</span></span> <span data-ttu-id="de9f2-139">當您設定這些規則時，請記下電話內容 (，也就是/Location 設定檔或/SimpleName) 和內部/外部區功能變數代碼，如此一來，您就可以在建立使用者時進行指定。</span><span class="sxs-lookup"><span data-stu-id="de9f2-139">When you're configuring these rules, take note of the phone context (that is, /Location Profile or /SimpleName) and Internal/External Area Codes, so that you can specify them when creating users.</span></span> <span data-ttu-id="de9f2-140">您也需要在 LyncPerfTool 設定 (期間特別針對 PSTN UC 和 UC-PSTN) 。</span><span class="sxs-lookup"><span data-stu-id="de9f2-140">You'll also need them during LyncPerfTool configuration (specifically for PSTN-UC and UC-PSTN).</span></span>
  
<span data-ttu-id="de9f2-141">例如，在 RoutingRules.ps1 範例中對 **get-csdialplan 指令程式** 的呼叫中，SimpleName 參數應該用於下列 UserProfileGenerator.exe 中的 microsoft.rtc.management.writableconfig.policy.voice.locationprofile 值：</span><span class="sxs-lookup"><span data-stu-id="de9f2-141">For example, the SimpleName parameter in the call to the **New-CsDialPlan** cmdlet in the RoutingRules.ps1 example should be used for the LocationProfile value in the following figure of UserProfileGenerator.exe:</span></span>
  
![商務用 Skype 載入設定工具、語音案例] 索引標籤、[交談的高級設定]。](../../media/59f42e4e-8f1e-4d43-9ae2-9e6026191951.png)
  
<span data-ttu-id="de9f2-143">如需詳細資訊，您可以複查 Enterprise Voice Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="de9f2-143">For details, you can review the Enterprise Voice cmdlets.</span></span>
  
## <a name="conference-attendant-application"></a><span data-ttu-id="de9f2-144">會議助理應用程式</span><span class="sxs-lookup"><span data-stu-id="de9f2-144">Conference Attendant application</span></span>
<span data-ttu-id="de9f2-145"><a name="ConfAttendantApp"> </a></span><span class="sxs-lookup"><span data-stu-id="de9f2-145"><a name="ConfAttendantApp"> </a></span></span>

<span data-ttu-id="de9f2-146">請先複查 ConferenceAutoAttendantConfiguration.ps1 腳本。</span><span class="sxs-lookup"><span data-stu-id="de9f2-146">First review the ConferenceAutoAttendantConfiguration.ps1 script.</span></span> <span data-ttu-id="de9f2-147">您會想記下 ConferencingAutoAttendant 的電話號碼 (1121111111 預設) ，所以您可以將它輸入 LyncPerfTool 設定工具進行設定產生，如下所示：</span><span class="sxs-lookup"><span data-stu-id="de9f2-147">You'll want to take note of the ConferencingAutoAttendant phone number (1121111111 by default), so that you can enter it into the LyncPerfTool configuration tool for configuration generation, as below:</span></span>
  
![語音案例] 索引標籤顯示會議的負載層級和電話號碼。](../../media/a3ea5fc0-8b3d-4842-b809-f137f470dbdc.png)
  
<span data-ttu-id="de9f2-149">您會在會議和電話撥入式會議 Cmdlet 中找到更多詳細資料。</span><span class="sxs-lookup"><span data-stu-id="de9f2-149">You'll find more details in the Conferencing and Dial-in Conferencing cmdlets.</span></span>
  
## <a name="server-call-park-service"></a><span data-ttu-id="de9f2-150">伺服器呼叫駐留服務</span><span class="sxs-lookup"><span data-stu-id="de9f2-150">Server Call Park service</span></span>
<span data-ttu-id="de9f2-151"><a name="ServerCallParkServ"> </a></span><span class="sxs-lookup"><span data-stu-id="de9f2-151"><a name="ServerCallParkServ"> </a></span></span>

<span data-ttu-id="de9f2-152">這實際上會預設為停用。</span><span class="sxs-lookup"><span data-stu-id="de9f2-152">This is actually disabled by default.</span></span> <span data-ttu-id="de9f2-153">您可以在需要測試時，複查 CallParkConfiguration.ps1 範例腳本。</span><span class="sxs-lookup"><span data-stu-id="de9f2-153">You can review the CallParkConfiguration.ps1 sample script if you need to test this.</span></span> <span data-ttu-id="de9f2-154">此外，視需要取出通話駐留應用程式 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="de9f2-154">Additionally, check out the Call Park Application cmdlets as needed.</span></span>
  
## <a name="emergency-calls"></a><span data-ttu-id="de9f2-155">緊急通話</span><span class="sxs-lookup"><span data-stu-id="de9f2-155">Emergency calls</span></span>
<span data-ttu-id="de9f2-156"><a name="EmergencyCalls"> </a></span><span class="sxs-lookup"><span data-stu-id="de9f2-156"><a name="EmergencyCalls"> </a></span></span>

<span data-ttu-id="de9f2-157">您必須執行下列步驟，為緊急通話設定壓力和效能測試：</span><span class="sxs-lookup"><span data-stu-id="de9f2-157">You'll need to perform the following steps to configure stress and performance testing for emergency calls:</span></span>
  
1. <span data-ttu-id="de9f2-158">設定緊急通話的語音路由。</span><span class="sxs-lookup"><span data-stu-id="de9f2-158">Set up a voice route for emergency calls.</span></span> <span data-ttu-id="de9f2-159">您可以使用 RoutingRules.ps1 腳本，然後查看批註「 **路由 E911 至 PSTN** 」，以取得如何設定此語音路由的範例。</span><span class="sxs-lookup"><span data-stu-id="de9f2-159">You can use the RoutingRules.ps1 script, and check under the comment " **Route E911 to PSTN** " for an example of how to set up this voice route.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="de9f2-160">RoutingRules.ps1 的範例命令具有數位模式，其中包含數位119，而不是911。</span><span class="sxs-lookup"><span data-stu-id="de9f2-160">The example command in RoutingRules.ps1 has a number pattern that includes the number 119 rather than 911.</span></span> <span data-ttu-id="de9f2-161">您應避免使用 911 (或實際的本機緊急號碼，) 以避免在負載測試期間意外呼叫本機緊急操作員。</span><span class="sxs-lookup"><span data-stu-id="de9f2-161">You should avoid using 911 (or your actual local emergency number) to prevent accidental calls to your local emergency operators during your load testing.</span></span> <span data-ttu-id="de9f2-162">請記住，此設定只是用於類比目的！</span><span class="sxs-lookup"><span data-stu-id="de9f2-162">Remember, this configuration is for simulation purposes only!</span></span> 
  
2. <span data-ttu-id="de9f2-163">填寫 UserProvisioningTool 中的 [ **位置資訊服務配置** ] 索引標籤上的值以設定位址，如下圖所示：</span><span class="sxs-lookup"><span data-stu-id="de9f2-163">Configure addresses by filling in the values on the **Location Info Service Config** tab in the UserProvisioningTool, as shown in the following figure:</span></span>
    
     ![使用者布建工具，顯示位址、子網、交換器和埠的數目。](../../media/ebe85a0c-750f-4301-97d4-d158a40ea98a.png)
  
3. <span data-ttu-id="de9f2-165">當您已在 UserProvisioningTool 中輸入內容時，請按一下 [ **產生 .lis 的 Config Files** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="de9f2-165">When you've entered everything into the UserProvisioningTool, click the **Generate LIS Config Files** button.</span></span>
    
4. <span data-ttu-id="de9f2-166">現在會產生壓力和效能工具 (Wap) 的埠、子網、交換器和無線存取點的 CSV 檔案。</span><span class="sxs-lookup"><span data-stu-id="de9f2-166">Now CSV files for ports, subnets, switches, and wireless access points (WAPs), as well as an XML file for the Stress and Performance tool will be generated.</span></span> <span data-ttu-id="de9f2-167">設定 Location 資訊服務 (.LIS) 使用 LisConfiguration.ps1 腳本時，您可以使用 CSV 檔案進行輸入。</span><span class="sxs-lookup"><span data-stu-id="de9f2-167">You can use the CSV files for inputs when configuring the Location Information service (LIS) with the LisConfiguration.ps1 script.</span></span> <span data-ttu-id="de9f2-168">若要這麼做，您必須將 Locations0.xml 檔案移至與壓力和效能工具可執行檔 ( # A1) 相同的資料夾。</span><span class="sxs-lookup"><span data-stu-id="de9f2-168">To do this, you'll need to move the Locations0.xml file to the same folder as the Stress and Performance Tool executable (LyncPerfTool.exe).</span></span> <span data-ttu-id="de9f2-169">這可讓您執行位置設定檔 (撥號對應表) 案例。</span><span class="sxs-lookup"><span data-stu-id="de9f2-169">This will let you run location profile (dial plan) scenarios.</span></span>
    
## <a name="configuring-response-group-application"></a><span data-ttu-id="de9f2-170">設定回應群組應用程式</span><span class="sxs-lookup"><span data-stu-id="de9f2-170">Configuring Response Group application</span></span>
<span data-ttu-id="de9f2-171"><a name="ConfigResponseGroupApp"> </a></span><span class="sxs-lookup"><span data-stu-id="de9f2-171"><a name="ConfigResponseGroupApp"> </a></span></span>

<span data-ttu-id="de9f2-172">範例腳本是 ResponseGroupConfiguration.ps1。</span><span class="sxs-lookup"><span data-stu-id="de9f2-172">The sample script is ResponseGroupConfiguration.ps1.</span></span> <span data-ttu-id="de9f2-173">還有其他的回應群組應用程式 Cmdlet 可供您複查，以取得進一步的設定詳細資料。</span><span class="sxs-lookup"><span data-stu-id="de9f2-173">There are also Response Group application cmdlets to review for further configuration details.</span></span> <span data-ttu-id="de9f2-174">下列圖表會顯示部分設定的詳細資料：</span><span class="sxs-lookup"><span data-stu-id="de9f2-174">The following diagram will show some of the configuration details:</span></span>
  
![回應群組 config 工具，顯示用於測試的現有工作流程。](../../media/e218a345-4813-4332-8cff-b48de05017ef.jpg)
  

