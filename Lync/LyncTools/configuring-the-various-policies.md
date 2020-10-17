---
title: 設定各種原則
description: 設定各種原則。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Configuring the Various Policies
ms:assetid: e3b3cbda-7c17-470b-acb0-82fdcc473184
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945610(v=OCS.15)
ms:contentKeyID: 51541436
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 746d299ac605c7dfe89a957246d47309dfbc0a5d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548839"
---
# <a name="configuring-the-various-policies"></a><span data-ttu-id="f8e34-103">設定各種原則</span><span class="sxs-lookup"><span data-stu-id="f8e34-103">Configuring the Various Policies</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8e34-104">_**主題上次修改日期：** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="f8e34-104">_**Topic Last Modified:** 2013-02-24_</span></span>

<div>

<span data-ttu-id="f8e34-105">以下是在執行 Lync Server 2013 壓力和效能工具之前，可在 Lync Server 2013 拓撲中設定的各種原則。</span><span class="sxs-lookup"><span data-stu-id="f8e34-105">Here are the various policies that you can configure in your Lync Server 2013 topology, prior to running the Lync Server 2013 Stress and Performance Tool.</span></span>

<div>

## <a name="configuring-the-archiving-policy"></a><span data-ttu-id="f8e34-106">設定封存原則</span><span class="sxs-lookup"><span data-stu-id="f8e34-106">Configuring the Archiving Policy</span></span>

<span data-ttu-id="f8e34-107">請參閱範例腳本 ArchivingPolicy.ps1。</span><span class="sxs-lookup"><span data-stu-id="f8e34-107">See the example script ArchivingPolicy.ps1.</span></span> <span data-ttu-id="f8e34-108">只有當封存伺服器部署在拓撲中時，您才需要使用此腳本。</span><span class="sxs-lookup"><span data-stu-id="f8e34-108">You need to use this script only if an Archiving Server is deployed in your topology.</span></span> <span data-ttu-id="f8e34-109">如需詳細資訊，請參閱 Lync server 2013 檔和 Cmdlet [在 Lync server 2013 中的封存及監控 Cmdlet](https://technet.microsoft.com/library/gg415629\(v=ocs.15\))。</span><span class="sxs-lookup"><span data-stu-id="f8e34-109">For details, see the Lync Server 2013 documentation and cmdlet Help for [Archiving and Monitoring cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415629\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-the-conferencing-policy"></a><span data-ttu-id="f8e34-110">設定會議原則</span><span class="sxs-lookup"><span data-stu-id="f8e34-110">Configuring the Conferencing Policy</span></span>

<span data-ttu-id="f8e34-111">請參閱範例腳本 MeetingPolicy.ps1。</span><span class="sxs-lookup"><span data-stu-id="f8e34-111">See the example script MeetingPolicy.ps1.</span></span> <span data-ttu-id="f8e34-112">如需詳細資訊，請參閱 lync server 2013 中的 Lync Server 2013 檔和 Cmdlet 說明（ [Web 會議 Cmdlet](https://technet.microsoft.com/library/gg415675\(v=ocs.15\))）。</span><span class="sxs-lookup"><span data-stu-id="f8e34-112">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Web conferencing cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415675\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-the-contacts-policy"></a><span data-ttu-id="f8e34-113">設定連絡人原則</span><span class="sxs-lookup"><span data-stu-id="f8e34-113">Configuring the Contacts Policy</span></span>

<span data-ttu-id="f8e34-114">請參閱範例 ContactsPolicy.ps1。</span><span class="sxs-lookup"><span data-stu-id="f8e34-114">See the example ContactsPolicy.ps1.</span></span> <span data-ttu-id="f8e34-115">如需詳細資訊，請參閱 Lync server 2013 檔以及 [Lync server 2013 中的 IM 和目前狀態 Cmdlet](https://technet.microsoft.com/library/gg398611\(v=ocs.15\))的 Cmdlet 說明。</span><span class="sxs-lookup"><span data-stu-id="f8e34-115">For details, see the Lync Server 2013 documentation and the cmdlet Help for [IM and presence cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg398611\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-the-federation-policy"></a><span data-ttu-id="f8e34-116">設定同盟原則</span><span class="sxs-lookup"><span data-stu-id="f8e34-116">Configuring the Federation Policy</span></span>

<span data-ttu-id="f8e34-117">請參閱範例 FederationPolicy.ps1。</span><span class="sxs-lookup"><span data-stu-id="f8e34-117">See the example FederationPolicy.ps1.</span></span> <span data-ttu-id="f8e34-118">如需詳細資訊，請參閱 lync server [2013 中的 Edge server Cmdlet](https://technet.microsoft.com/library/gg415635\(v=ocs.15\)) 的 lync server 2013 檔和 Cmdlet 說明，以及 [lync server 2013 中的同盟與外部訪問 Cmdlet](https://technet.microsoft.com/library/gg415651\(v=ocs.15\))。</span><span class="sxs-lookup"><span data-stu-id="f8e34-118">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Edge Server cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415635\(v=ocs.15\)) and [Federation and external access cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415651\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-the-call-admission-control-policy"></a><span data-ttu-id="f8e34-119">設定通話許可控制原則</span><span class="sxs-lookup"><span data-stu-id="f8e34-119">Configuring the Call Admission Control Policy</span></span>

<span data-ttu-id="f8e34-120">請參閱範例 BandwidthPolicy.ps1。</span><span class="sxs-lookup"><span data-stu-id="f8e34-120">See the example BandwidthPolicy.ps1.</span></span> <span data-ttu-id="f8e34-121">如需詳細資訊，請參閱 lync server [2013 中通話許可控制](https://technet.microsoft.com/library/gg398529\(v=ocs.15\)) 的 [lync server 2013] 檔概述，以及 [lync Server 2013 中通話許可控制 Cmdlet](https://technet.microsoft.com/library/gg415676\(v=ocs.15\))的 Cmdlet 說明。</span><span class="sxs-lookup"><span data-stu-id="f8e34-121">For details, see the Lync Server 2013 documentation [Overview of call admission control in Lync Server 2013](https://technet.microsoft.com/library/gg398529\(v=ocs.15\)) and the cmdlet Help for [Call admission control cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415676\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-the-voice-routing-rules"></a><span data-ttu-id="f8e34-122">設定語音路由規則</span><span class="sxs-lookup"><span data-stu-id="f8e34-122">Configuring the Voice Routing Rules</span></span>

<span data-ttu-id="f8e34-123">請參閱範例 RoutingRules.ps1。</span><span class="sxs-lookup"><span data-stu-id="f8e34-123">See the example RoutingRules.ps1.</span></span> <span data-ttu-id="f8e34-124">當您設定語音路由規則時，請記下電話內容 (，也就是/Location 設定檔或/SimpleName) 和內部/外部區號，如此一來，您就可以在建立使用者時和 (LyncPerfTool 設定期間，特別針對 PSTN UC 和 UC-PSTN) 加以指定。</span><span class="sxs-lookup"><span data-stu-id="f8e34-124">When you configure the voice routing rules, take note of the Phone Context (that is, /Location Profile or /SimpleName) and Internal/External Area Codes so that you can specify them when creating users and during LyncPerfTool configuration (specifically for PSTN-UC and UC-PSTN).</span></span> <span data-ttu-id="f8e34-125">例如，在 RoutingRules.ps1 範例中對 **get-csdialplan 指令程式** 的呼叫中，SimpleName 參數應該用於 UserProfileGenerator.exe 的下圖中的 microsoft.rtc.management.writableconfig.policy.voice.locationprofile 值。</span><span class="sxs-lookup"><span data-stu-id="f8e34-125">For example, the SimpleName parameter in the call to the **New-CsDialPlan** cmdlet in the RoutingRules.ps1 example should be used for the LocationProfile value in the following figure of UserProfileGenerator.exe.</span></span>

<span data-ttu-id="f8e34-126">![語音路由規則範例。](images/JJ945610.9f34d971-4ed0-4a4c-b101-086a91c4578c(OCS.15).jpg "語音路由規則範例。")</span><span class="sxs-lookup"><span data-stu-id="f8e34-126">![Sample voice routing rule.](images/JJ945610.9f34d971-4ed0-4a4c-b101-086a91c4578c(OCS.15).jpg "Sample voice routing rule.")</span></span>

<span data-ttu-id="f8e34-127">如需詳細資訊，請參閱 lync server 2013 中的 [Lync Server 2013] 檔和 [Cmdlet 說明] [中的 Enterprise Voice Cmdlet](https://technet.microsoft.com/library/gg415658\(v=ocs.15\))。</span><span class="sxs-lookup"><span data-stu-id="f8e34-127">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Enterprise Voice cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415658\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-conferencing-attendant-application"></a><span data-ttu-id="f8e34-128">設定會議助理應用程式</span><span class="sxs-lookup"><span data-stu-id="f8e34-128">Configuring Conferencing Attendant application</span></span>

<span data-ttu-id="f8e34-129">請參閱範例 ConferenceAutoAttendantConfiguration.ps1。</span><span class="sxs-lookup"><span data-stu-id="f8e34-129">See the example ConferenceAutoAttendantConfiguration.ps1.</span></span> <span data-ttu-id="f8e34-130">請記下 ConferencingAutoAttendant 的電話號碼 (1121111111，依預設) ，所以您可以將它輸入 LyncPerf 工具設定工具，以進行設定產生。</span><span class="sxs-lookup"><span data-stu-id="f8e34-130">Take note of the ConferencingAutoAttendant phone number (1121111111, by default), so that you can type it into the LyncPerf Tool Configuration tool for configuration generation.</span></span>

<span data-ttu-id="f8e34-131">![設定會議助理應用程式](images/JJ945610.0618a22f-27a9-423a-9085-d2bf71e82db6(OCS.15).jpg "設定會議助理應用程式")</span><span class="sxs-lookup"><span data-stu-id="f8e34-131">![Configuring the Conferencing Attendant application](images/JJ945610.0618a22f-27a9-423a-9085-d2bf71e82db6(OCS.15).jpg "Configuring the Conferencing Attendant application")</span></span>

<span data-ttu-id="f8e34-132">如需詳細資訊，請參閱 lync server 2013 和 lync server 2013 中的 Lync server 2013 和[電話撥入式會議 Cmdlet](https://technet.microsoft.com/library/gg415630\(v=ocs.15\))[中的 Web 會議 Cmdlet](https://technet.microsoft.com/library/gg415675\(v=ocs.15\))的 Lync server 檔和 Cmdlet 說明。</span><span class="sxs-lookup"><span data-stu-id="f8e34-132">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Web conferencing cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415675\(v=ocs.15\)) and [Dial-in conferencing cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415630\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-lync-server-call-park-service"></a><span data-ttu-id="f8e34-133">設定 Lync Server 通話駐留服務</span><span class="sxs-lookup"><span data-stu-id="f8e34-133">Configuring Lync Server Call Park Service</span></span>

<span data-ttu-id="f8e34-134">通話駐留預設為停用。</span><span class="sxs-lookup"><span data-stu-id="f8e34-134">Call Park is disabled by default.</span></span> <span data-ttu-id="f8e34-135">請參閱範例 CallParkConfiguration.ps1。</span><span class="sxs-lookup"><span data-stu-id="f8e34-135">See the example CallParkConfiguration.ps1.</span></span> <span data-ttu-id="f8e34-136">如需詳細資訊，請參閱 Lync server 2013 檔和 Cmdlet Help for the [Lync server 2013 中的通話駐留應用程式 Cmdlet](https://technet.microsoft.com/library/gg415639\(v=ocs.15\))。</span><span class="sxs-lookup"><span data-stu-id="f8e34-136">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Call Park application cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415639\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-emergency-calls"></a><span data-ttu-id="f8e34-137">設定緊急通話</span><span class="sxs-lookup"><span data-stu-id="f8e34-137">Configuring Emergency Calls</span></span>

<span data-ttu-id="f8e34-138">執行下列步驟，為緊急通話設定壓力和效能測試。</span><span class="sxs-lookup"><span data-stu-id="f8e34-138">Perform the following steps to configure stress and performance testing for emergency calls.</span></span>

1.  <span data-ttu-id="f8e34-139">設定緊急通話的語音路由。</span><span class="sxs-lookup"><span data-stu-id="f8e34-139">Set up a voice route for emergency calls.</span></span> <span data-ttu-id="f8e34-140">如需設定這個語音路由的範例，請參閱批註「Route E911 to PSTN」下的 RoutingRules.ps1 腳本。</span><span class="sxs-lookup"><span data-stu-id="f8e34-140">See the RoutingRules.ps1 script under the comment "Route E911 to PSTN" for an example of setting up this voice route.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="f8e34-141">RoutingRules.ps1 的範例命令具有數位模式，其中包含數位119，而不是911。</span><span class="sxs-lookup"><span data-stu-id="f8e34-141">The example command in RoutingRules.ps1 has a number pattern that includes the number 119 rather than 911.</span></span> <span data-ttu-id="f8e34-142">您應避免使用 911 (或實際的本機緊急號碼，) 以避免在負載測試期間意外呼叫本機緊急操作員。</span><span class="sxs-lookup"><span data-stu-id="f8e34-142">You should avoid using 911 (or your actual local emergency number) to prevent accidental calls to your local emergency operators during load testing.</span></span> <span data-ttu-id="f8e34-143">此設定僅供類比之用。</span><span class="sxs-lookup"><span data-stu-id="f8e34-143">This configuration is for simulation purposes only.</span></span>

    
    </div>

2.  <span data-ttu-id="f8e34-144">填寫 UserProvisioningTool 中的 [所有 **.lis** ] 索引標籤上的值以設定位址，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="f8e34-144">Configure addresses by filling in the values on the **LIS** tab in the UserProvisioningTool, as shown in the following figure.</span></span>
    
    <span data-ttu-id="f8e34-145">![設定位置資訊服務。](images/JJ945610.8ac1faa1-e9f9-40d0-b8b7-b159f4f459f7(OCS.15).jpg "設定位置資訊服務。")</span><span class="sxs-lookup"><span data-stu-id="f8e34-145">![Configuring the Location Information Service.](images/JJ945610.8ac1faa1-e9f9-40d0-b8b7-b159f4f459f7(OCS.15).jpg "Configuring the Location Information Service.")</span></span>  

3.  <span data-ttu-id="f8e34-146">按一下 [ **產生 .lis 的設定檔**]。</span><span class="sxs-lookup"><span data-stu-id="f8e34-146">Click **Generate LIS Config Files**.</span></span>

4.  <span data-ttu-id="f8e34-147">會產生 (Wap) 的埠、子網、交換器和無線存取點的 CSV 檔案，以及 Lync Server 2013 壓力和效能工具的 XML 檔案。</span><span class="sxs-lookup"><span data-stu-id="f8e34-147">CSV files for ports, subnets, switches, and wireless access points (WAPs), and an XML file for the Lync Server 2013 Stress and Performance Tool, are generated.</span></span> <span data-ttu-id="f8e34-148">設定 Location 資訊服務 (.LIS) 與 LisConfiguration.ps1 腳本時，會使用 CSV 檔案做為相同資料夾中 (的輸入) 。</span><span class="sxs-lookup"><span data-stu-id="f8e34-148">The CSV files are to be used as inputs (in the same folder) when configuring Location Information service (LIS) with the LisConfiguration.ps1 script.</span></span> <span data-ttu-id="f8e34-149">將產生的 Locations0.xml 檔案移動到 Lync Server 2013 應力和效能工具可執行檔 ( # A1) ，該資料夾會執行位置設定檔 (撥號對應表) 案例。</span><span class="sxs-lookup"><span data-stu-id="f8e34-149">Move the generated Locations0.xml file to the same folder as the Lync Server 2013 Stress and Performance Tool executable (LyncPerfTool.exe), which will run location profile (dial plan) scenarios.</span></span>

</div>

<div>

## <a name="creating-enabling-configuring-and-disabling-users"></a><span data-ttu-id="f8e34-150">建立、啟用、設定及停用使用者</span><span class="sxs-lookup"><span data-stu-id="f8e34-150">Creating, Enabling, Configuring and Disabling Users</span></span>

<span data-ttu-id="f8e34-151">在執行下列腳本之前，您應該先建立所有使用者。</span><span class="sxs-lookup"><span data-stu-id="f8e34-151">You should create all your users before running the following scripts.</span></span> <span data-ttu-id="f8e34-152">依照 [建立使用者和連絡人](create-users-and-contacts.md) 以建立使用者的指示進行。</span><span class="sxs-lookup"><span data-stu-id="f8e34-152">Follow the instructions in [Create Users and Contacts](create-users-and-contacts.md) to create users.</span></span> <span data-ttu-id="f8e34-153">如需詳細資訊，請參閱 Lync Server 2013 Cmdlet 檔，以取得 [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\))、 [Set-CsUser](https://technet.microsoft.com/library/gg398510\(v=ocs.15\))和 [get-csuser](https://technet.microsoft.com/library/gg398747\(v=ocs.15\)) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f8e34-153">For details, see the Lync Server 2013 cmdlet documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)), [Set-CsUser](https://technet.microsoft.com/library/gg398510\(v=ocs.15\)), and [Disable-CsUser](https://technet.microsoft.com/library/gg398747\(v=ocs.15\)) cmdlets.</span></span>

</div>

<div>

## <a name="configuring-response-group-application"></a><span data-ttu-id="f8e34-154">設定回應群組應用程式</span><span class="sxs-lookup"><span data-stu-id="f8e34-154">Configuring Response Group application</span></span>

<span data-ttu-id="f8e34-155">請參閱範例 ResponseGroupConfiguration.ps1。</span><span class="sxs-lookup"><span data-stu-id="f8e34-155">See the example ResponseGroupConfiguration.ps1.</span></span> <span data-ttu-id="f8e34-156">如需詳細資訊，請參閱 Lync server 2013 檔和 Cmdlet 說明，以瞭解 [Lync server 2013 中的回應群組應用程式 Cmdlet](https://technet.microsoft.com/library/gg415654\(v=ocs.15\))。若要複查回應群組應用程式設定，請參閱 `https://<poolfqdn>/RgsConfig/` ，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="f8e34-156">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Response Group application cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415654\(v=ocs.15\)).To review the Response Group application configuration, see `https://<poolfqdn>/RgsConfig/`, as shown in the following figure.</span></span>

<span data-ttu-id="f8e34-157">![回應群組設定工具。](images/JJ945610.480a9440-2283-4533-98f8-86daaab4781c(OCS.15).jpg "回應群組設定工具。")</span><span class="sxs-lookup"><span data-stu-id="f8e34-157">![The Response Group Configuration Tool.](images/JJ945610.480a9440-2283-4533-98f8-86daaab4781c(OCS.15).jpg "The Response Group Configuration Tool.")</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

