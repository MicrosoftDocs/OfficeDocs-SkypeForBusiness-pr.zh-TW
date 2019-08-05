---
title: 設定商務用 Skype Server 2015 應力與效能工具的原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 11/11/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7e1435e2-d073-4265-8067-ebcb5bf28835
description: 商務用 Skype Server 2015 應力與效能工具的原則設定。
ms.openlocfilehash: 5c8e4c296d06c736519a12da5b5e34c6f48e9ee2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193139"
---
# <a name="configuring-policies-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a><span data-ttu-id="9525c-103">設定商務用 Skype Server 2015 應力與效能工具的原則</span><span class="sxs-lookup"><span data-stu-id="9525c-103">Configuring policies for the Skype for Business Server 2015 Stress and Performance Tool</span></span>
 
<span data-ttu-id="9525c-104">商務用 Skype Server 2015 應力與效能工具的原則設定。</span><span class="sxs-lookup"><span data-stu-id="9525c-104">Policy configuration for Skype for Business Server 2015 Stress and Performance Tool.</span></span>
  
<span data-ttu-id="9525c-105">在執行壓力與效能工具之前, 您可以在商務用 Skype Server 2015 中設定數個原則和其他區域:</span><span class="sxs-lookup"><span data-stu-id="9525c-105">There are several policies and other areas that you can configure in Skype for Business Server 2015, prior to running the Stress and Performance Tool:</span></span>
  
- [<span data-ttu-id="9525c-106">存檔原則</span><span class="sxs-lookup"><span data-stu-id="9525c-106">Archiving policy</span></span>](configuring-policies.md#ArchivingPolicy)
    
- [<span data-ttu-id="9525c-107">會議原則</span><span class="sxs-lookup"><span data-stu-id="9525c-107">Conferencing policy</span></span>](configuring-policies.md#ConferencingPolicy)
    
- [<span data-ttu-id="9525c-108">連絡人原則</span><span class="sxs-lookup"><span data-stu-id="9525c-108">Contacts policy</span></span>](configuring-policies.md#ContactsPolicy)
    
- [<span data-ttu-id="9525c-109">同盟原則</span><span class="sxs-lookup"><span data-stu-id="9525c-109">Federation policy</span></span>](configuring-policies.md#FederationPolicy)
    
- [<span data-ttu-id="9525c-110">呼叫許可控制原則</span><span class="sxs-lookup"><span data-stu-id="9525c-110">Call Admission Control policy</span></span>](configuring-policies.md#CACPolicy)
    
- [<span data-ttu-id="9525c-111">語音路由規則</span><span class="sxs-lookup"><span data-stu-id="9525c-111">Voice Routing rules</span></span>](configuring-policies.md#VoiceRoutingRules)
    
- [<span data-ttu-id="9525c-112">會議助理應用程式</span><span class="sxs-lookup"><span data-stu-id="9525c-112">Conference Attendant application</span></span>](configuring-policies.md#ConfAttendantApp)
    
- [<span data-ttu-id="9525c-113">伺服器通話駐留服務</span><span class="sxs-lookup"><span data-stu-id="9525c-113">Server Call Park service</span></span>](configuring-policies.md#ServerCallParkServ)
    
- [<span data-ttu-id="9525c-114">緊急通話</span><span class="sxs-lookup"><span data-stu-id="9525c-114">Emergency calls</span></span>](configuring-policies.md#EmergencyCalls)
    
- [<span data-ttu-id="9525c-115">配置回應群組應用程式</span><span class="sxs-lookup"><span data-stu-id="9525c-115">Configuring Response Group application</span></span>](configuring-policies.md#ConfigResponseGroupApp)
    
## <a name="archiving-policy"></a><span data-ttu-id="9525c-116">存檔原則</span><span class="sxs-lookup"><span data-stu-id="9525c-116">Archiving policy</span></span>
<span data-ttu-id="9525c-117"><a name="ArchivingPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="9525c-117"></span></span>

<span data-ttu-id="9525c-118">如果您在商務用 Skype Server 拓撲結構中部署了封存伺服器, 您可以查看 ArchivingPolicy. ps1 腳本。</span><span class="sxs-lookup"><span data-stu-id="9525c-118">If you have an Archiving server deployed in your Skype for Business Server topology, you can look at the ArchivingPolicy.ps1 script.</span></span> <span data-ttu-id="9525c-119">如果您需要進一步協助, 請查看 [封存] 和 [Web 會議] Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9525c-119">If you need further assistance, check out the Archiving and Web Conferencing cmdlets.</span></span>
  
## <a name="conferencing-policy"></a><span data-ttu-id="9525c-120">會議原則</span><span class="sxs-lookup"><span data-stu-id="9525c-120">Conferencing policy</span></span>
<span data-ttu-id="9525c-121"><a name="ConferencingPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="9525c-121"></span></span>

<span data-ttu-id="9525c-122">對於會議, 我們有 MeetingPolicy. ps1 腳本。</span><span class="sxs-lookup"><span data-stu-id="9525c-122">For conferencing, we have the MeetingPolicy.ps1 script.</span></span> <span data-ttu-id="9525c-123">如果您需要進一步協助, 請查看網路會議 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9525c-123">If you need further assistance, check out the Web Conferencing cmdlets.</span></span>
  
## <a name="contacts-policy"></a><span data-ttu-id="9525c-124">連絡人原則</span><span class="sxs-lookup"><span data-stu-id="9525c-124">Contacts policy</span></span>
<span data-ttu-id="9525c-125"><a name="ContactsPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="9525c-125"></span></span>

<span data-ttu-id="9525c-126">ContactsPolicy. ps1 腳本將是您需要檢查的範例。</span><span class="sxs-lookup"><span data-stu-id="9525c-126">ContactsPolicy.ps1 script will be the sample you'll need to review.</span></span> <span data-ttu-id="9525c-127">如果您需要進一步參考, IM 和目前狀態 Cmdlet 會有所説明。</span><span class="sxs-lookup"><span data-stu-id="9525c-127">The IM and Presence cmdlets will help if you need further references.</span></span>
  
## <a name="federation-policy"></a><span data-ttu-id="9525c-128">同盟原則</span><span class="sxs-lookup"><span data-stu-id="9525c-128">Federation policy</span></span>
<span data-ttu-id="9525c-129"><a name="FederationPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="9525c-129"></span></span>

<span data-ttu-id="9525c-130">同盟的範例腳本是 FederationPolicy. ps1........。</span><span class="sxs-lookup"><span data-stu-id="9525c-130">The sample script for federation is FederationPolicy.ps1.</span></span> <span data-ttu-id="9525c-131">若要查看的 Cmdlet (如果您需要進一步瞭解) 將會是 Edge 伺服器、同盟和外部存取。</span><span class="sxs-lookup"><span data-stu-id="9525c-131">The cmdlets to review, if you need further insight, will be Edge Server, federation, and external access.</span></span>
  
## <a name="call-admission-control-policy"></a><span data-ttu-id="9525c-132">呼叫許可控制原則</span><span class="sxs-lookup"><span data-stu-id="9525c-132">Call Admission Control policy</span></span>
<span data-ttu-id="9525c-133"><a name="CACPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="9525c-133"></span></span>

<span data-ttu-id="9525c-134">您可以參考此原則的 BandwidthPolicy. ps1。</span><span class="sxs-lookup"><span data-stu-id="9525c-134">You can reference BandwidthPolicy.ps1 for this policy.</span></span> <span data-ttu-id="9525c-135">通話許可控制 Cmdlet 也會有進一步的資訊。</span><span class="sxs-lookup"><span data-stu-id="9525c-135">The Call Admission Control cmdlets will have further information as well.</span></span>
  
## <a name="voice-routing-rules"></a><span data-ttu-id="9525c-136">語音路由規則</span><span class="sxs-lookup"><span data-stu-id="9525c-136">Voice Routing rules</span></span>
<span data-ttu-id="9525c-137"><a name="VoiceRoutingRules"> </a></span><span class="sxs-lookup"><span data-stu-id="9525c-137"></span></span>

<span data-ttu-id="9525c-138">您需要 RoutingRules. ps1 語音路由範例腳本。</span><span class="sxs-lookup"><span data-stu-id="9525c-138">You'll need the RoutingRules.ps1 sample script for Voice Routing.</span></span> <span data-ttu-id="9525c-139">當您設定這些規則時, 請記下電話內容 (也就是/Location 設定檔或/SimpleName) 及內部/外部區功能變數代碼, 以便在建立使用者時加以指定。</span><span class="sxs-lookup"><span data-stu-id="9525c-139">When you're configuring these rules, take note of the phone context (that is, /Location Profile or /SimpleName) and Internal/External Area Codes, so that you can specify them when creating users.</span></span> <span data-ttu-id="9525c-140">在 LyncPerfTool 設定期間, 您也需要他們 (特別是 PSTN UC 與 UC)。</span><span class="sxs-lookup"><span data-stu-id="9525c-140">You'll also need them during LyncPerfTool configuration (specifically for PSTN-UC and UC-PSTN).</span></span>
  
<span data-ttu-id="9525c-141">例如, RoutingRules. ps1 中的**CsDialPlan** Cmdlet 呼叫中的 SimpleName 參數應該用於 UserProfileGenerator 中下圖中的 LocationProfile 值 ..:</span><span class="sxs-lookup"><span data-stu-id="9525c-141">For example, the SimpleName parameter in the call to the **New-CsDialPlan** cmdlet in the RoutingRules.ps1 example should be used for the LocationProfile value in the following figure of UserProfileGenerator.exe:</span></span>
  
![商務用 Skype 負載組態工具、語音案例索引標籤、交談的高級設定。](../../media/59f42e4e-8f1e-4d43-9ae2-9e6026191951.png)
  
<span data-ttu-id="9525c-143">如需詳細資訊, 您可以查看企業語音 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9525c-143">For details, you can review the Enterprise Voice cmdlets.</span></span>
  
## <a name="conference-attendant-application"></a><span data-ttu-id="9525c-144">會議助理應用程式</span><span class="sxs-lookup"><span data-stu-id="9525c-144">Conference Attendant application</span></span>
<span data-ttu-id="9525c-145"><a name="ConfAttendantApp"> </a></span><span class="sxs-lookup"><span data-stu-id="9525c-145"></span></span>

<span data-ttu-id="9525c-146">首先, 請複習 ConferenceAutoAttendantConfiguration. ps1 腳本。</span><span class="sxs-lookup"><span data-stu-id="9525c-146">First review the ConferenceAutoAttendantConfiguration.ps1 script.</span></span> <span data-ttu-id="9525c-147">您會想記下 ConferencingAutoAttendant 的電話號碼 (預設為 1121111111), 以便將它輸入到 LyncPerfTool 設定工具中以進行配置產生, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="9525c-147">You'll want to take note of the ConferencingAutoAttendant phone number (1121111111 by default), so that you can enter it into the LyncPerfTool configuration tool for configuration generation, as below:</span></span>
  
![[語音案例] 索引標籤顯示會議載入等級和電話號碼。](../../media/a3ea5fc0-8b3d-4842-b809-f137f470dbdc.png)
  
<span data-ttu-id="9525c-149">您可以在會議和電話撥入式會議 Cmdlet 中找到更多詳細資料。</span><span class="sxs-lookup"><span data-stu-id="9525c-149">You'll find more details in the Conferencing and Dial-in Conferencing cmdlets.</span></span>
  
## <a name="server-call-park-service"></a><span data-ttu-id="9525c-150">伺服器通話駐留服務</span><span class="sxs-lookup"><span data-stu-id="9525c-150">Server Call Park service</span></span>
<span data-ttu-id="9525c-151"><a name="ServerCallParkServ"> </a></span><span class="sxs-lookup"><span data-stu-id="9525c-151"></span></span>

<span data-ttu-id="9525c-152">預設會停用此功能。</span><span class="sxs-lookup"><span data-stu-id="9525c-152">This is actually disabled by default.</span></span> <span data-ttu-id="9525c-153">您可以查看 CallParkConfiguration. ps1 範例腳本 (如果您需要測試此選項)。</span><span class="sxs-lookup"><span data-stu-id="9525c-153">You can review the CallParkConfiguration.ps1 sample script if you need to test this.</span></span> <span data-ttu-id="9525c-154">此外, 視需要查看通話寄存應用程式 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="9525c-154">Additionally, check out the Call Park Application cmdlets as needed.</span></span>
  
## <a name="emergency-calls"></a><span data-ttu-id="9525c-155">緊急通話</span><span class="sxs-lookup"><span data-stu-id="9525c-155">Emergency calls</span></span>
<span data-ttu-id="9525c-156"><a name="EmergencyCalls"> </a></span><span class="sxs-lookup"><span data-stu-id="9525c-156"></span></span>

<span data-ttu-id="9525c-157">您需要執行下列步驟來設定緊急通話的壓力與效能測試:</span><span class="sxs-lookup"><span data-stu-id="9525c-157">You'll need to perform the following steps to configure stress and performance testing for emergency calls:</span></span>
  
1. <span data-ttu-id="9525c-158">設定緊急通話的語音路線。</span><span class="sxs-lookup"><span data-stu-id="9525c-158">Set up a voice route for emergency calls.</span></span> <span data-ttu-id="9525c-159">您可以使用 RoutingRules. ps1 腳本, 然後檢查 [**路由 E911 至 PSTN** ] 批註, 以取得如何設定此語音路由的範例。</span><span class="sxs-lookup"><span data-stu-id="9525c-159">You can use the RoutingRules.ps1 script, and check under the comment " **Route E911 to PSTN** " for an example of how to set up this voice route.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="9525c-160">RoutingRules 中的範例命令有一個數位模式, 其中包含數位 119, 而不是911。</span><span class="sxs-lookup"><span data-stu-id="9525c-160">The example command in RoutingRules.ps1 has a number pattern that includes the number 119 rather than 911.</span></span> <span data-ttu-id="9525c-161">您應該避免使用 911 (或您的實際當地緊急號碼) 來避免在負載測試期間意外呼叫本機緊急操作員。</span><span class="sxs-lookup"><span data-stu-id="9525c-161">You should avoid using 911 (or your actual local emergency number) to prevent accidental calls to your local emergency operators during your load testing.</span></span> <span data-ttu-id="9525c-162">請記住, 此設定僅適用于模擬目的!</span><span class="sxs-lookup"><span data-stu-id="9525c-162">Remember, this configuration is for simulation purposes only!</span></span> 
  
2. <span data-ttu-id="9525c-163">透過在 UserProvisioningTool 中的**位置資訊服務 [配置**] 索引標籤上填入值來設定位址, 如下圖所示:</span><span class="sxs-lookup"><span data-stu-id="9525c-163">Configure addresses by filling in the values on the **Location Info Service Config** tab in the UserProvisioningTool, as shown in the following figure:</span></span>
    
     ![[使用者供給] 工具, 顯示位址數量、子網、切換和埠數。](../../media/ebe85a0c-750f-4301-97d4-d158a40ea98a.png)
  
3. <span data-ttu-id="9525c-165">當您在 UserProvisioningTool 中輸入所有專案時, 請按一下 [**產生 .lis 使用者配置**檔案] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="9525c-165">When you've entered everything into the UserProvisioningTool, click the **Generate LIS Config Files** button.</span></span>
    
4. <span data-ttu-id="9525c-166">現在會產生用於埠、子網、開關和無線存取點 (WAPs) 的 CSV 檔案, 以及用於壓力與效能工具的 XML 檔案。</span><span class="sxs-lookup"><span data-stu-id="9525c-166">Now CSV files for ports, subnets, switches, and wireless access points (WAPs), as well as an XML file for the Stress and Performance tool will be generated.</span></span> <span data-ttu-id="9525c-167">將位置資訊服務 (.LIS) 與 LisConfiguration. ps1 腳本進行設定時, 您可以使用 CSV 檔案進行輸入。</span><span class="sxs-lookup"><span data-stu-id="9525c-167">You can use the CSV files for inputs when configuring the Location Information service (LIS) with the LisConfiguration.ps1 script.</span></span> <span data-ttu-id="9525c-168">若要這樣做, 您需要將 Locations0 檔案移至與壓力和效能工具可執行檔 (LyncPerfTool) 相同的資料夾。</span><span class="sxs-lookup"><span data-stu-id="9525c-168">To do this, you'll need to move the Locations0.xml file to the same folder as the Stress and Performance Tool executable (LyncPerfTool.exe).</span></span> <span data-ttu-id="9525c-169">這可讓您執行位置設定檔 (撥號方案) 案例。</span><span class="sxs-lookup"><span data-stu-id="9525c-169">This will let you run location profile (dial plan) scenarios.</span></span>
    
## <a name="configuring-response-group-application"></a><span data-ttu-id="9525c-170">配置回應群組應用程式</span><span class="sxs-lookup"><span data-stu-id="9525c-170">Configuring Response Group application</span></span>
<span data-ttu-id="9525c-171"><a name="ConfigResponseGroupApp"> </a></span><span class="sxs-lookup"><span data-stu-id="9525c-171"></span></span>

<span data-ttu-id="9525c-172">範例腳本為 ResponseGroupConfiguration. ps1........。</span><span class="sxs-lookup"><span data-stu-id="9525c-172">The sample script is ResponseGroupConfiguration.ps1.</span></span> <span data-ttu-id="9525c-173">還有回應群組應用程式 Cmdlet 可供您審查進一步的配置詳細資料。</span><span class="sxs-lookup"><span data-stu-id="9525c-173">There are also Response Group application cmdlets to review for further configuration details.</span></span> <span data-ttu-id="9525c-174">下列圖表會顯示一些配置詳細資料:</span><span class="sxs-lookup"><span data-stu-id="9525c-174">The following diagram will show some of the configuration details:</span></span>
  
![回應群組的 [config] 工具, 顯示測試的現有工作流程。](../../media/e218a345-4813-4332-8cff-b48de05017ef.jpg)
  

