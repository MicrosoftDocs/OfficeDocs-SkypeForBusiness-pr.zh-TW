---
title: 設定各種原則
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Configuring the Various Policies
ms:assetid: e3b3cbda-7c17-470b-acb0-82fdcc473184
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945610(v=OCS.15)
ms:contentKeyID: 51541436
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a105ea62b82d904007a2faa0493fd17092b84462
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974860"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-various-policies"></a><span data-ttu-id="0c47a-102">設定各種原則</span><span class="sxs-lookup"><span data-stu-id="0c47a-102">Configuring the Various Policies</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0c47a-103">_**主題上次修改日期：** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="0c47a-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<div>

## <a name="configuring-the-various-policies"></a><span data-ttu-id="0c47a-104">設定各種原則</span><span class="sxs-lookup"><span data-stu-id="0c47a-104">Configuring the Various Policies</span></span>

<span data-ttu-id="0c47a-105">以下是您可以在 Lync Server 2013 拓撲中設定的各種原則，在執行 Lync Server 2013 的壓力和效能工具之前。</span><span class="sxs-lookup"><span data-stu-id="0c47a-105">Here are the various policies that you can configure in your Lync Server 2013 topology, prior to running the Lync Server 2013 Stress and Performance Tool.</span></span>

<div>

## <a name="configuring-the-archiving-policy"></a><span data-ttu-id="0c47a-106">設定存檔原則</span><span class="sxs-lookup"><span data-stu-id="0c47a-106">Configuring the Archiving Policy</span></span>

<span data-ttu-id="0c47a-107">請參閱範例腳本 ArchivingPolicy. ps1。</span><span class="sxs-lookup"><span data-stu-id="0c47a-107">See the example script ArchivingPolicy.ps1.</span></span> <span data-ttu-id="0c47a-108">只有在您的拓撲中部署了存檔伺服器時，才能使用此腳本。</span><span class="sxs-lookup"><span data-stu-id="0c47a-108">You need to use this script only if an Archiving Server is deployed in your topology.</span></span> <span data-ttu-id="0c47a-109">如需詳細資訊，請參閱 lync server 2013 檔和 Cmdlet[在 Lync server 2013 中的存檔與監控 Cmdlet](https://technet.microsoft.com/en-us/library/gg415629\(v=ocs.15\))說明。</span><span class="sxs-lookup"><span data-stu-id="0c47a-109">For details, see the Lync Server 2013 documentation and cmdlet Help for [Archiving and Monitoring cmdlets in Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415629\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-the-conferencing-policy"></a><span data-ttu-id="0c47a-110">設定會議原則</span><span class="sxs-lookup"><span data-stu-id="0c47a-110">Configuring the Conferencing Policy</span></span>

<span data-ttu-id="0c47a-111">請參閱範例腳本 MeetingPolicy. ps1。</span><span class="sxs-lookup"><span data-stu-id="0c47a-111">See the example script MeetingPolicy.ps1.</span></span> <span data-ttu-id="0c47a-112">如需詳細資訊，請參閱 lync server 2013 檔和[Lync server 2013 中的 Web 會議](https://technet.microsoft.com/en-us/library/gg415675\(v=ocs.15\))Cmdlet Cmdlet 說明。</span><span class="sxs-lookup"><span data-stu-id="0c47a-112">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Web conferencing cmdlets in Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415675\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-the-contacts-policy"></a><span data-ttu-id="0c47a-113">設定連絡人原則</span><span class="sxs-lookup"><span data-stu-id="0c47a-113">Configuring the Contacts Policy</span></span>

<span data-ttu-id="0c47a-114">請參閱範例 ContactsPolicy. ps1。</span><span class="sxs-lookup"><span data-stu-id="0c47a-114">See the example ContactsPolicy.ps1.</span></span> <span data-ttu-id="0c47a-115">如需詳細資訊，請參閱 lync Server 2013 檔和[Lync server 2013 中的 IM 和目前狀態 Cmdlet](https://technet.microsoft.com/en-us/library/gg398611\(v=ocs.15\))的 Cmdlet 說明。</span><span class="sxs-lookup"><span data-stu-id="0c47a-115">For details, see the Lync Server 2013 documentation and the cmdlet Help for [IM and presence cmdlets in Lync Server 2013](https://technet.microsoft.com/en-us/library/gg398611\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-the-federation-policy"></a><span data-ttu-id="0c47a-116">配置同盟原則</span><span class="sxs-lookup"><span data-stu-id="0c47a-116">Configuring the Federation Policy</span></span>

<span data-ttu-id="0c47a-117">請參閱範例 FederationPolicy. ps1。</span><span class="sxs-lookup"><span data-stu-id="0c47a-117">See the example FederationPolicy.ps1.</span></span> <span data-ttu-id="0c47a-118">如需詳細資訊，請參閱 lync server 2013 檔和 lync server 2013 中的 [lync server 2013] 和 [[同盟與外部存取 Cmdlet](https://technet.microsoft.com/en-us/library/gg415651\(v=ocs.15\))] 中的 [ [Edge 伺服器 Cmdlet](https://technet.microsoft.com/en-us/library/gg415635\(v=ocs.15\)) ] Cmdlet 說明。</span><span class="sxs-lookup"><span data-stu-id="0c47a-118">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Edge Server cmdlets in Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415635\(v=ocs.15\)) and [Federation and external access cmdlets in Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415651\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-the-call-admission-control-policy"></a><span data-ttu-id="0c47a-119">設定通話許可控制原則</span><span class="sxs-lookup"><span data-stu-id="0c47a-119">Configuring the Call Admission Control Policy</span></span>

<span data-ttu-id="0c47a-120">請參閱範例 BandwidthPolicy. ps1。</span><span class="sxs-lookup"><span data-stu-id="0c47a-120">See the example BandwidthPolicy.ps1.</span></span> <span data-ttu-id="0c47a-121">如需詳細資訊，2013請參閱 lync server [2013 中的通話許可控制](https://technet.microsoft.com/en-us/library/gg398529\(v=ocs.15\))說明，以及[lync Server 2013 中通話許可控制 Cmdlet](https://technet.microsoft.com/en-us/library/gg415676\(v=ocs.15\))的 Cmdlet 說明。</span><span class="sxs-lookup"><span data-stu-id="0c47a-121">For details, see the Lync Server 2013 documentation [Overview of call admission control in Lync Server 2013](https://technet.microsoft.com/en-us/library/gg398529\(v=ocs.15\)) and the cmdlet Help for [Call admission control cmdlets in Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415676\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-the-voice-routing-rules"></a><span data-ttu-id="0c47a-122">設定語音路由規則</span><span class="sxs-lookup"><span data-stu-id="0c47a-122">Configuring the Voice Routing Rules</span></span>

<span data-ttu-id="0c47a-123">請參閱範例 RoutingRules. ps1。</span><span class="sxs-lookup"><span data-stu-id="0c47a-123">See the example RoutingRules.ps1.</span></span> <span data-ttu-id="0c47a-124">當您設定語音路由規則時，請記下手機內容（即/Location 設定檔或/SimpleName）及內部/外部區功能變數代碼，讓您在建立使用者時和 LyncPerfTool 設定期間（特別是 PSTN UC 與 UC）進行指定。</span><span class="sxs-lookup"><span data-stu-id="0c47a-124">When you configure the voice routing rules, take note of the Phone Context (that is, /Location Profile or /SimpleName) and Internal/External Area Codes so that you can specify them when creating users and during LyncPerfTool configuration (specifically for PSTN-UC and UC-PSTN).</span></span> <span data-ttu-id="0c47a-125">例如，在 RoutingRules. ps1 中，對**CsDialPlan** Cmdlet 的呼叫中的 SimpleName 參數，都應該用於 UserProfileGenerator 下圖中的 LocationProfile 值。</span><span class="sxs-lookup"><span data-stu-id="0c47a-125">For example, the SimpleName parameter in the call to the **New-CsDialPlan** cmdlet in the RoutingRules.ps1 example should be used for the LocationProfile value in the following figure of UserProfileGenerator.exe.</span></span>

<span data-ttu-id="0c47a-126">![語音路由規則範例。](images/JJ945610.9f34d971-4ed0-4a4c-b101-086a91c4578c(OCS.15).jpg "語音路由規則範例。")</span><span class="sxs-lookup"><span data-stu-id="0c47a-126">![Sample voice routing rule.](images/JJ945610.9f34d971-4ed0-4a4c-b101-086a91c4578c(OCS.15).jpg "Sample voice routing rule.")</span></span>

<span data-ttu-id="0c47a-127">如需詳細資訊，請參閱 lync server 2013 檔和[Lync server 2013 中企業語音 Cmdlet](https://technet.microsoft.com/en-us/library/gg415658\(v=ocs.15\))的 Cmdlet 說明。</span><span class="sxs-lookup"><span data-stu-id="0c47a-127">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Enterprise Voice cmdlets in Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415658\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-conferencing-attendant-application"></a><span data-ttu-id="0c47a-128">設定會議助理應用程式</span><span class="sxs-lookup"><span data-stu-id="0c47a-128">Configuring Conferencing Attendant application</span></span>

<span data-ttu-id="0c47a-129">請參閱範例 ConferenceAutoAttendantConfiguration. ps1。</span><span class="sxs-lookup"><span data-stu-id="0c47a-129">See the example ConferenceAutoAttendantConfiguration.ps1.</span></span> <span data-ttu-id="0c47a-130">記下 ConferencingAutoAttendant 的電話號碼（預設為1121111111），這樣您就可以將它輸入到 LyncPerf 工具設定工具中，以進行配置產生。</span><span class="sxs-lookup"><span data-stu-id="0c47a-130">Take note of the ConferencingAutoAttendant phone number (1121111111, by default), so that you can type it into the LyncPerf Tool Configuration tool for configuration generation.</span></span>

<span data-ttu-id="0c47a-131">設定![會議助理應用程式，]以設定(images/JJ945610.0618a22f-27a9-423a-9085-d2bf71e82db6(OCS.15).jpg "會議助理應用程式")</span><span class="sxs-lookup"><span data-stu-id="0c47a-131">![Configuring the Conferencing Attendant application](images/JJ945610.0618a22f-27a9-423a-9085-d2bf71e82db6(OCS.15).jpg "Configuring the Conferencing Attendant application")</span></span>

<span data-ttu-id="0c47a-132">如需詳細資訊，請參閱 lync server 2013 檔和 lync server 2013 中的[Lync server 2013](https://technet.microsoft.com/en-us/library/gg415675\(v=ocs.15\))和[電話撥入式會議 Cmdlet](https://technet.microsoft.com/en-us/library/gg415630\(v=ocs.15\))中的 Web 會議 Cmdlet Cmdlet 說明。</span><span class="sxs-lookup"><span data-stu-id="0c47a-132">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Web conferencing cmdlets in Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415675\(v=ocs.15\)) and [Dial-in conferencing cmdlets in Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415630\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-lync-server-call-park-service"></a><span data-ttu-id="0c47a-133">正在設定 Lync Server 通話寄存服務</span><span class="sxs-lookup"><span data-stu-id="0c47a-133">Configuring Lync Server Call Park Service</span></span>

<span data-ttu-id="0c47a-134">通話駐留預設為停用。</span><span class="sxs-lookup"><span data-stu-id="0c47a-134">Call Park is disabled by default.</span></span> <span data-ttu-id="0c47a-135">請參閱範例 CallParkConfiguration. ps1。</span><span class="sxs-lookup"><span data-stu-id="0c47a-135">See the example CallParkConfiguration.ps1.</span></span> <span data-ttu-id="0c47a-136">如需詳細資訊，請參閱 lync server 2013 檔和[Lync server 2013 中通話駐留應用程式 Cmdlet](https://technet.microsoft.com/en-us/library/gg415639\(v=ocs.15\))的 Cmdlet 說明。</span><span class="sxs-lookup"><span data-stu-id="0c47a-136">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Call Park application cmdlets in Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415639\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-emergency-calls"></a><span data-ttu-id="0c47a-137">設定緊急通話</span><span class="sxs-lookup"><span data-stu-id="0c47a-137">Configuring Emergency Calls</span></span>

<span data-ttu-id="0c47a-138">請執行下列步驟來設定緊急通話的壓力和效能測試。</span><span class="sxs-lookup"><span data-stu-id="0c47a-138">Perform the following steps to configure stress and performance testing for emergency calls.</span></span>

1.  <span data-ttu-id="0c47a-139">設定緊急通話的語音路線。</span><span class="sxs-lookup"><span data-stu-id="0c47a-139">Set up a voice route for emergency calls.</span></span> <span data-ttu-id="0c47a-140">如需設定此語音路由的範例，請參閱 [路由 E911 至 PSTN] 批註下的 RoutingRules 腳本。</span><span class="sxs-lookup"><span data-stu-id="0c47a-140">See the RoutingRules.ps1 script under the comment "Route E911 to PSTN" for an example of setting up this voice route.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="0c47a-141">RoutingRules 中的範例命令有一個數位模式，其中包含數位119，而不是911。</span><span class="sxs-lookup"><span data-stu-id="0c47a-141">The example command in RoutingRules.ps1 has a number pattern that includes the number 119 rather than 911.</span></span> <span data-ttu-id="0c47a-142">您應該避免使用911（或您的實際當地緊急號碼）來避免在負載測試期間意外呼叫本機緊急操作員。</span><span class="sxs-lookup"><span data-stu-id="0c47a-142">You should avoid using 911 (or your actual local emergency number) to prevent accidental calls to your local emergency operators during load testing.</span></span> <span data-ttu-id="0c47a-143">此設定僅供模擬之用。</span><span class="sxs-lookup"><span data-stu-id="0c47a-143">This configuration is for simulation purposes only.</span></span>

    
    </div>

2.  <span data-ttu-id="0c47a-144">您可以在 UserProvisioningTool 中的 [**宏] 索引標籤上填入**值來設定位址，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="0c47a-144">Configure addresses by filling in the values on the **LIS** tab in the UserProvisioningTool, as shown in the following figure.</span></span>
    
    <span data-ttu-id="0c47a-145">![配置位置資訊服務。](images/JJ945610.8ac1faa1-e9f9-40d0-b8b7-b159f4f459f7(OCS.15).jpg "配置位置資訊服務。")</span><span class="sxs-lookup"><span data-stu-id="0c47a-145">![Configuring the Location Information Service.](images/JJ945610.8ac1faa1-e9f9-40d0-b8b7-b159f4f459f7(OCS.15).jpg "Configuring the Location Information Service.")</span></span>  

3.  <span data-ttu-id="0c47a-146">按一下 [**產生 .Lis 設定檔**]。</span><span class="sxs-lookup"><span data-stu-id="0c47a-146">Click **Generate LIS Config Files**.</span></span>

4.  <span data-ttu-id="0c47a-147">會產生埠、子網、開關和無線存取點（WAPs）的 CSV 檔案，以及 Lync Server 2013 應力和效能工具的 XML 檔案。</span><span class="sxs-lookup"><span data-stu-id="0c47a-147">CSV files for ports, subnets, switches, and wireless access points (WAPs), and an XML file for the Lync Server 2013 Stress and Performance Tool, are generated.</span></span> <span data-ttu-id="0c47a-148">當您使用 LisConfiguration. ps1 腳本設定位置資訊服務（.LIS）時，CSV 檔案會當作輸入（在同一個資料夾中）使用。</span><span class="sxs-lookup"><span data-stu-id="0c47a-148">The CSV files are to be used as inputs (in the same folder) when configuring Location Information service (LIS) with the LisConfiguration.ps1 script.</span></span> <span data-ttu-id="0c47a-149">將產生的 Locations0 檔案移至 Lync Server 2013 應力和效能工具可執行檔（LyncPerfTool）的相同資料夾中，這將會執行位置設定檔（撥號方案）。</span><span class="sxs-lookup"><span data-stu-id="0c47a-149">Move the generated Locations0.xml file to the same folder as the Lync Server 2013 Stress and Performance Tool executable (LyncPerfTool.exe), which will run location profile (dial plan) scenarios.</span></span>

</div>

<div>

## <a name="creating-enabling-configuring-and-disabling-users"></a><span data-ttu-id="0c47a-150">建立、啟用、設定及停用使用者</span><span class="sxs-lookup"><span data-stu-id="0c47a-150">Creating, Enabling, Configuring and Disabling Users</span></span>

<span data-ttu-id="0c47a-151">在執行下列腳本前，您應該先建立所有的使用者。</span><span class="sxs-lookup"><span data-stu-id="0c47a-151">You should create all your users before running the following scripts.</span></span> <span data-ttu-id="0c47a-152">依照[建立使用者和連絡人](create-users-and-contacts.md)中的指示來建立使用者。</span><span class="sxs-lookup"><span data-stu-id="0c47a-152">Follow the instructions in [Create Users and Contacts](create-users-and-contacts.md) to create users.</span></span> <span data-ttu-id="0c47a-153">如需詳細資訊，請參閱適用于[move-csuser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\))、 [Move-csuser](https://technet.microsoft.com/en-us/library/gg398510\(v=ocs.15\))和[Disable move-csuser](https://technet.microsoft.com/en-us/library/gg398747\(v=ocs.15\)) Cmdlet 的 Lync Server 2013 Cmdlet 檔。</span><span class="sxs-lookup"><span data-stu-id="0c47a-153">For details, see the Lync Server 2013 cmdlet documentation for the [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)), [Set-CsUser](https://technet.microsoft.com/en-us/library/gg398510\(v=ocs.15\)), and [Disable-CsUser](https://technet.microsoft.com/en-us/library/gg398747\(v=ocs.15\)) cmdlets.</span></span>

</div>

<div>

## <a name="configuring-response-group-application"></a><span data-ttu-id="0c47a-154">配置回應群組應用程式</span><span class="sxs-lookup"><span data-stu-id="0c47a-154">Configuring Response Group application</span></span>

<span data-ttu-id="0c47a-155">請參閱範例 ResponseGroupConfiguration. ps1。</span><span class="sxs-lookup"><span data-stu-id="0c47a-155">See the example ResponseGroupConfiguration.ps1.</span></span> <span data-ttu-id="0c47a-156">如需詳細資訊，請參閱 lync server 2013 檔和適用于[Lync server 2013 中之回應群組應用程式 Cmdlet](https://technet.microsoft.com/en-us/library/gg415654\(v=ocs.15\))的 Cmdlet 說明。若要查看回應群組應用程式設定， `https://<poolfqdn>/RgsConfig/`請參閱，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="0c47a-156">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Response Group application cmdlets in Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415654\(v=ocs.15\)).To review the Response Group application configuration, see `https://<poolfqdn>/RgsConfig/`, as shown in the following figure.</span></span>

<span data-ttu-id="0c47a-157">![[回應群組設定] 工具。](images/JJ945610.480a9440-2283-4533-98f8-86daaab4781c(OCS.15).jpg "[回應群組設定] 工具。")</span><span class="sxs-lookup"><span data-stu-id="0c47a-157">![The Response Group Configuration Tool.](images/JJ945610.480a9440-2283-4533-98f8-86daaab4781c(OCS.15).jpg "The Response Group Configuration Tool.")</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

