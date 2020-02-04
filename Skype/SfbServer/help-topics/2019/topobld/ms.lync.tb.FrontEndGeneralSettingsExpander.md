---
title: 前端一般設定展開工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.FrontEndGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8a5f21d0-f6c8-4907-9958-5ca36f702542
ROBOTS: NOINDEX, NOFOLLOW
description: 為編輯現有前端集區或 Standard Edition Server 的設定，我們為您提供了下列幾個區段：
ms.openlocfilehash: 76992a6d88c25a1907e4bb2cc1f6dee69a418f01
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41688509"
---
# <a name="front-end-general-settings-expander"></a><span data-ttu-id="557dd-103">前端一般設定展開工具</span><span class="sxs-lookup"><span data-stu-id="557dd-103">Front End General Settings Expander</span></span>

<span data-ttu-id="557dd-104">為編輯現有前端集區或 Standard Edition Server 的設定，我們為您提供了下列幾個區段：</span><span class="sxs-lookup"><span data-stu-id="557dd-104">To edit the settings for an existing Front End pool or Standard Edition server, you are presented with the following sections:</span></span>

- <span data-ttu-id="557dd-105">一般設定</span><span class="sxs-lookup"><span data-stu-id="557dd-105">General settings</span></span>

- <span data-ttu-id="557dd-106">恢復設定</span><span class="sxs-lookup"><span data-stu-id="557dd-106">Resiliency settings</span></span>

- <span data-ttu-id="557dd-107">Web 服務設定</span><span class="sxs-lookup"><span data-stu-id="557dd-107">Web services settings</span></span>

- <span data-ttu-id="557dd-108">中繼伺服器設定</span><span class="sxs-lookup"><span data-stu-id="557dd-108">Mediation Server settings</span></span>

## <a name="front-end-pool"></a><span data-ttu-id="557dd-109">前端集區</span><span class="sxs-lookup"><span data-stu-id="557dd-109">Front End pool</span></span>

<span data-ttu-id="557dd-p101">您可以針對前端集區設定一般、恢復、Web 服務以及中繼伺服器的相關設定。如需詳細資訊，請參閱以下各小節中的資訊。如需定義和設定前端集區各項設定的詳細資訊，請參閱〈[Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx)〉。</span><span class="sxs-lookup"><span data-stu-id="557dd-p101">For a Front End pool, you can configure general, resiliency, web services, and Mediation Server settings. For details, see the information in the following subsections. For details about defining and configuring the settings for the Front End pool, see [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).</span></span>

### <a name="general-settings"></a><span data-ttu-id="557dd-113">一般設定</span><span class="sxs-lookup"><span data-stu-id="557dd-113">General Settings</span></span>

<span data-ttu-id="557dd-114">您可以設定下列一般設定：</span><span class="sxs-lookup"><span data-stu-id="557dd-114">You can configure the following general settings:</span></span>

- <span data-ttu-id="557dd-p102">**FQDN**。編輯集區的 FQDN 以進行變更。</span><span class="sxs-lookup"><span data-stu-id="557dd-p102">**FQDN**. Edit the FQDN of the pool to change it.</span></span>

- <span data-ttu-id="557dd-p103">**啟用硬體負載平衡器監控連接埠**。選取核取方塊，然後輸入硬體負載平衡器將用以監控集區伺服器狀態的連接埠號碼。</span><span class="sxs-lookup"><span data-stu-id="557dd-p103">**Enable hardware load balancer monitoring port**. Select the check box and enter the port number that your Hardware Load Balancer will use to monitor the state of the pool servers.</span></span>

- <span data-ttu-id="557dd-p104">在 [功能]\*\*\*\* 中，定義想要與此集區組合的其他角色。您可以設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="557dd-p104">In **Features and Functionality**, define the additional roles that you want to collocate with this pool. You can configure the following settings:</span></span>

  - <span data-ttu-id="557dd-p105">**會議**。包含音訊、視訊與應用程式共用。選取此選項後，您可以選取 [電話撥入式 (PSTN) 會議]。在稍後〈中繼伺服器設定〉小節中，指定和定義公用交換電話網路 (PSTN) 閘道。</span><span class="sxs-lookup"><span data-stu-id="557dd-p105">**Conferencing**. Includes audio, video and application sharing. After you select this option, you can select Dial-in (PSTN) conferencing. You specify and define a public switched telephone network (PSTN) gateway in the "Mediation Server Settings" subsection later in this section.</span></span>

  - <span data-ttu-id="557dd-125">**企業語音**。</span><span class="sxs-lookup"><span data-stu-id="557dd-125">**Enterprise Voice**.</span></span> <span data-ttu-id="557dd-126">在合格的手機和裝置以及商務用 Skype 用戶端啟用內部的語音 over IP 通話。</span><span class="sxs-lookup"><span data-stu-id="557dd-126">Enables internal voice over IP calls to qualified handsets and devices and Skype for Business clients.</span></span> <span data-ttu-id="557dd-127">若要啟用外部通話功能，需要包括中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="557dd-127">To enable external call capabilities, you need to include a Mediation Server.</span></span> <span data-ttu-id="557dd-128">如需詳細資訊，請參閱本主題稍後的〈中繼伺服器〉。</span><span class="sxs-lookup"><span data-stu-id="557dd-128">For details, see "Mediation Server" later in this topic.</span></span>

- <span data-ttu-id="557dd-129">在 [關聯]\*\*\*\* 中，編輯或指定下列項目：</span><span class="sxs-lookup"><span data-stu-id="557dd-129">In **Associations**, edit or specify the following:</span></span>

  - <span data-ttu-id="557dd-p107">**SQL 存放區**。修改現有的 SQL Server 資料庫或建立新的 SQL Server 資料庫，以存放前端集區資料庫。您可以從清單中選取新的 SQL Server 執行個體，或按一下 [新增]\*\*\*\* 建立新的項目。</span><span class="sxs-lookup"><span data-stu-id="557dd-p107">**SQL Store**. Modify an existing SQL Server database or create a new SQL Server-based database to hold the Front End pool databases. You can select a new instance of SQL Server from the list or create a new entry by clicking **New**.</span></span>

    <span data-ttu-id="557dd-p108">選取 [啟用 SQL Server 儲存區鏡像]\*\*\*\*，然後選取要用於鏡像的伺服器。按一下 [新增]\*\*\*\* 建立新的 SQL Server 儲存區。</span><span class="sxs-lookup"><span data-stu-id="557dd-p108">Select **Enable SQL Server store mirroring**, and then select the server to use for mirroring. Click **New** to create a new SQL Server store.</span></span>

    <span data-ttu-id="557dd-p109">選取 [使用 SQL Server 鏡像見證啟用自動容錯移轉]\*\*\*\*，以選取要作為鏡像見證的伺服器。按一下 [新增]\*\*\*\* 建立新的 SQL Server 儲存區。</span><span class="sxs-lookup"><span data-stu-id="557dd-p109">Select **Use SQL Server mirroring witness to enable automatic failover** to select a server to use as a mirroring witness. Click **New** to create a new SQL Server store.</span></span>

  - <span data-ttu-id="557dd-p110">**檔案共用**。修改前端集區所使用的檔案存放區。您可以從先前已定義的檔案存放區中選取一個新的檔案存放區，方式是從清單中加以選取。您可以按一下 [新增]\*\*\*\*，以建立新的檔案存放區。</span><span class="sxs-lookup"><span data-stu-id="557dd-p110">**File share**. Modify the file store that the Front End pool is using. You can select a new file store from those already defined by selecting it from the list. You can create a new file store by clicking **New**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="557dd-141">您所指定的伺服器必須存在並加入網域中，您才能發行新定義的拓撲。</span><span class="sxs-lookup"><span data-stu-id="557dd-141">Before publishing the newly defined topology, the server that you specify must exist and be joined to the domain.</span></span>

  - <span data-ttu-id="557dd-p111">**封存**。建立封存伺服器儲存區與前端集區的關聯。您可以從清單中選取伺服器，以選取已定義的封存 SQL Server 儲存區，或按一下 [新增]\*\*\*\* 以指定新的封存伺服器。</span><span class="sxs-lookup"><span data-stu-id="557dd-p111">**Archiving**. Associate an Archiving Server store with the Front End pool. You can select from an already defined Archiving SQL Server store by selecting the server from the list, or click **New** to specify a new Archiving Server.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="557dd-145">您所指定的伺服器必須存在並加入網域中，您才能發行新定義的拓撲。</span><span class="sxs-lookup"><span data-stu-id="557dd-145">Before publishing the newly defined topology, the server that you specify must exist and be joined to the domain.</span></span>

    <span data-ttu-id="557dd-p112">選取 [啟用 SQL Server 儲存區鏡像]\*\*\*\*，然後選取要用於鏡像的伺服器。按一下 [新增]\*\*\*\* 建立新的 SQL Server 儲存區。</span><span class="sxs-lookup"><span data-stu-id="557dd-p112">Select **Enable SQL Server store mirroring**, and then select the server to use for mirroring. Click **New** to create a new SQL Server store.</span></span>

    <span data-ttu-id="557dd-p113">選取 [使用 SQL Server 鏡像見證啟用自動容錯移轉]\*\*\*\*，以選取要作為鏡像見證的伺服器。按一下 [新增]\*\*\*\* 建立新的 SQL Server 儲存區。</span><span class="sxs-lookup"><span data-stu-id="557dd-p113">Select **Use SQL Server mirroring witness to enable automatic failover** to select a server to use as a mirroring witness. Click **New** to create a new SQL Server store.</span></span>

  - <span data-ttu-id="557dd-p114">**監控 (CDR 和 QoE 計量)**。選取以建立監控 SQL Server 儲存區與前端集區的關聯。您可以從清單中選取伺服器，以選取已定義的監控伺服器，或按一下 [新增]\*\*\*\* 以指定新的監控伺服器。</span><span class="sxs-lookup"><span data-stu-id="557dd-p114">**Monitoring (CDR and QoE metrics)**. Select to associate a Monitoring SQL Server store with the Front End pool. You can select from an already defined Monitoring Server by selecting the server from the list, or click **New** to specify a new Monitoring Server.</span></span>

    <span data-ttu-id="557dd-p115">選取 [啟用 SQL Server 儲存區鏡像]\*\*\*\*，然後選取要用於鏡像的伺服器。按一下 [新增]\*\*\*\* 建立新的 SQL Server 儲存區。</span><span class="sxs-lookup"><span data-stu-id="557dd-p115">Select **Enable SQL Server store mirroring**, and then select the server to use for mirroring. Click **New** to create a new SQL Server store.</span></span>

    <span data-ttu-id="557dd-p116">選取 [使用 SQL Server 鏡像見證啟用自動容錯移轉]\*\*\*\*，以選取要作為鏡像見證的伺服器。按一下 [新增]\*\*\*\* 建立新的 SQL Server 儲存區。</span><span class="sxs-lookup"><span data-stu-id="557dd-p116">Select **Use SQL Server mirroring witness to enable automatic failover** to select a server to use as a mirroring witness. Click **New** to create a new SQL Server store.</span></span>

  - <span data-ttu-id="557dd-p117">**建立 Edge 集區的關聯 (用於媒體元件)**。建立 Edge Server 或集區與前端集區的關聯。您可以從清單中選取伺服器，以選取已定義的 Edge Server 或集區，或按一下 [新增]\*\*\*\* 以指定新的 Edge Server 或集區。</span><span class="sxs-lookup"><span data-stu-id="557dd-p117">**Associate Edge pool (for media components)**. Associate an Edge Server or pool with the Front End pool. You can select from an already defined Edge Server or pool by selecting the server from the list, or click **New** to specify a new Edge Server or pool.</span></span>

  - <span data-ttu-id="557dd-p118">**建立集區與 Office Web Apps Server 的關聯**。選取這個選項可建立 Office Web Apps Server 與前端集區的關聯。從清單中選取現有的伺服器，或按一下 [新增]\*\*\*\* 建立新的 Office Web Apps Server。</span><span class="sxs-lookup"><span data-stu-id="557dd-p118">**Associate pool with an Office Web Apps Server**. Select this option to associate an Office Web Apps Server with the Front End pool. Select an existing server from the list, or click **New** to create a new Office Web Apps Server.</span></span>

### <a name="resiliency"></a><span data-ttu-id="557dd-163">恢復</span><span class="sxs-lookup"><span data-stu-id="557dd-163">Resiliency</span></span>

<span data-ttu-id="557dd-p119">恢復功能提供集區的嚴重損壞修復和高可用性。藉由提供備份，如果主要伺服器失敗，則備份伺服器可以接管，讓使用者能夠進行登入和通訊。視無法使用主要伺服器的系統為何而定，使用者可用的功能可能會減少。</span><span class="sxs-lookup"><span data-stu-id="557dd-p119">Resiliency provides disaster recovery and high availability for the pool. By providing a backup, if the primary server fails, the backup server can take over, enabling users to sign in and communicate. There may be reduced functionality for users, depending on which systems have failed with the primary server.</span></span>

<span data-ttu-id="557dd-p120">從清單中選取將作為集區之備份伺服器的前端集區或 Standard Edition Server。您也可以選擇啟用「容錯移轉」與「容錯回復」時間間隔。啟用容錯移轉與容錯回復時間設定 (以秒為單位來指定) 可自動偵測失敗的伺服器，並且有容錯回復時間可自動判定是否已備份主要伺服器。</span><span class="sxs-lookup"><span data-stu-id="557dd-p120">From the list, select the Front End pool or Standard Edition server that will act as the backup server for the pool. You can also select to enable Failover and Fallback time intervals. Enabling the failover and fallback time settings (specified in seconds) enables automatic detection of a failed server, and a fallback time to allow for automatic determination that the primary is back up.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="557dd-p121">定義失敗偵測和容錯回復間隔時，請小心不要讓輸入的間隔導致在伺服器短時間無法回應時，發生容錯移轉和容錯回復。根據集區或伺服器的載入情形，主要伺服器可能會在短時間內無法回應。「集區對集區」或「集區對 Standard Edition Server」的容錯移轉與容錯回復預設值，分別為 300 秒與 600 秒。從網站中的 Survivable Branch Appliance 或 Survivable Branch 伺服器到集區或 Standard Edition Server，容錯移轉的預設值為 120 秒，容錯回復的預設值為 240 秒。</span><span class="sxs-lookup"><span data-stu-id="557dd-p121">When defining the Failure detection and the Fallback interval, you should be careful not to enter an interval that will cause the failover and fallback to occur if the server fails to respond for a short period of time. It is possible that the primary server may not respond for short periods of time, depending on the loading of the pool or servers. The default values for the failover and fallback are 300 seconds and 600 seconds for pool to pool, or pool to Standard Edition server. In the event of a Survivable Branch Appliance or a Survivable Branch Server in a site to a pool or Standard Edition server, the default values are 120 seconds for failover and 240 seconds for fallback.</span></span>

> [!CAUTION]
> <span data-ttu-id="557dd-p122">[容錯移轉間隔]\*\*\*\* 的最小值不可設定為低於 90 秒。如果您將該值設定為低於 90 秒，則會使用 90 秒的值。InterCluster Ping 時間為 30 秒，而設定低於 90 秒則有可能會導致主要和備份伺服器週期反覆，因此在伺服器嘗試解決其他伺服器的可用狀態時，會對生產環境造成不適當的影響。少於 90 秒的時間不足以判定主要伺服器是否確實無法使用。</span><span class="sxs-lookup"><span data-stu-id="557dd-p122">The minimum value for the **failover interval** should not be set lower than 90 seconds. If you do set the value to less than 90 seconds, the value of 90 seconds is used. The intercluster ping time is 30 seconds, and a setting lower than 90 seconds may cause the primary and backup servers to cycle up and down, causing an undesirable impact to production, as the servers try to resolve the viable status of the other. Less than 90 seconds does not allow for enough time to determine that the primary server is actually unavailable or not.</span></span>

### <a name="web-services"></a><span data-ttu-id="557dd-178">Web 服務</span><span class="sxs-lookup"><span data-stu-id="557dd-178">Web Services</span></span>

<span data-ttu-id="557dd-179">若要為前端集區上的 Web 服務編輯或指定其他設定，請修改或指定 [內部 Web 服務]\*\*\*\* 與 [外部 Web 服務]\*\*\*\* 中的設定。</span><span class="sxs-lookup"><span data-stu-id="557dd-179">To edit or specify additional setting for the web services on the Front End pool, modify or specify settings in **Internal Web services** and **External Web services**.</span></span>

<span data-ttu-id="557dd-180">在 [內部 Web 服務]\*\*\*\* 中，指定下列項目：</span><span class="sxs-lookup"><span data-stu-id="557dd-180">In **Internal Web services**, specify the following:</span></span>

> [!CAUTION]
> <span data-ttu-id="557dd-181">如果您有多個前端池或前端伺服器，則外部 Web 服務 FQDN 必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="557dd-181">If you have more than one Front End pool or Front End Server, the external Web services FQDN must be unique.</span></span> <span data-ttu-id="557dd-182">例如，如果您將前端伺服器的外部 Web 服務 FQDN 定義為**pool01.contoso.com**，則無法將**pool01.contoso.com**用於另一個前端池或前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="557dd-182">For example, if you define the external Web services FQDN of a Front End Server as **pool01.contoso.com**, you cannot use **pool01.contoso.com** for another Front End pool or Front End Server.</span></span> <span data-ttu-id="557dd-183">如果您也要部署控制器，則針對任何主管或主管池所定義的外部 Web 服務 FQDN，都必須是與任何其他控制器或主管池（以及來自任何前端池或前端伺服器）都是唯一的。</span><span class="sxs-lookup"><span data-stu-id="557dd-183">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool, as well as from any Front End pool or Front End Server.</span></span> <span data-ttu-id="557dd-184">如果您決定使用自行定義的 FQDN 來覆寫內部 web 服務，則每個 FQDN 都必須是與任何其他前端池、導演或控制器池都是唯一的。</span><span class="sxs-lookup"><span data-stu-id="557dd-184">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director, or Director pool.</span></span>

- <span data-ttu-id="557dd-p124">如果您選取 [覆寫 FQDN]\*\*\*\*，您可以為集區上的 [內部 Web]\*\*\*\* 服務識別指定不同的 FQDN。依預設，此設定是為前端集區定義的現行集區名稱。</span><span class="sxs-lookup"><span data-stu-id="557dd-p124">If you select **Override FQDN**, you can specify a different FQDN for the **Internal Web** services identity on the pool. By default, the setting is the current pool name as defined for the Front End pool.</span></span>

- <span data-ttu-id="557dd-p125">部署所需的 HTTP 與 HTTPS 之聆聽連接埠與發行的連接埠。最常見的設定是讓 HTTP 使用預設設定連接埠 80，讓 HTTPS 使用預設設定連接埠 443，且除非您的組織與基礎結構設計有特定需求，否則通常不需加以變更。</span><span class="sxs-lookup"><span data-stu-id="557dd-p125">Listening and published ports for HTTP and HTTPS that your deployment requires. The default settings of port 80 for HTTP and port 443 for HTTPS are the most common settings and typically do not need to be changed, unless you have specific requirements within your organization and infrastructure design.</span></span>

<span data-ttu-id="557dd-189">在 [外部 Web 服務]\*\*\*\* 中，指定下列項目：</span><span class="sxs-lookup"><span data-stu-id="557dd-189">In **External Web services**, specify the following:</span></span>

- <span data-ttu-id="557dd-p126">外部 Web 服務的 FQDN。此處指定的 FQDN 通常會依您外部連線的需求 (例如反向 Proxy) 而定義。</span><span class="sxs-lookup"><span data-stu-id="557dd-p126">The FQDN of the External Web services. The FQDN specified here will usually be defined by the requirements of your external connection requirements, such as the reverse proxy.</span></span>

- <span data-ttu-id="557dd-192">部署所需的 HTTP 與 HTTPS 之聆聽連接埠與發行的連接埠。</span><span class="sxs-lookup"><span data-stu-id="557dd-192">Listening and published ports for HTTP and HTTPS that your deployment requires.</span></span> <span data-ttu-id="557dd-193">HTTPS 的埠8080的預設設定與 HTTPS 的埠4443最初定義。</span><span class="sxs-lookup"><span data-stu-id="557dd-193">The default settings of port 8080 for HTTP and port 4443 for HTTPS are defined initially.</span></span> <span data-ttu-id="557dd-194">您可以根據您反向 Proxy 與外部網路的需求，為聆聽連接埠變更這些設定。</span><span class="sxs-lookup"><span data-stu-id="557dd-194">You change these settings for the listening ports based on what the requirements are for your reverse proxy and external network requirements.</span></span> <span data-ttu-id="557dd-195">已發佈的埠會設定為 HTTP 的埠80，以及 HTTPS 的埠443的預設值。</span><span class="sxs-lookup"><span data-stu-id="557dd-195">The published ports are set to default of port 80 for HTTP and port 443 for HTTPS.</span></span> <span data-ttu-id="557dd-196">這些值決定該池會偵聽傳入要求的埠。</span><span class="sxs-lookup"><span data-stu-id="557dd-196">These values determine what ports the pool will listen for incoming requests.</span></span> <span data-ttu-id="557dd-197">通常不需要變更這些功能，除非在該池有埠需求衝突的情況下。</span><span class="sxs-lookup"><span data-stu-id="557dd-197">Typically, these do not need to be changed, unless there is a conflict of port requirements on the pool.</span></span> <span data-ttu-id="557dd-198">需要使用相同埠值的內部和外部發佈埠。</span><span class="sxs-lookup"><span data-stu-id="557dd-198">Internal and external published ports using the same port values are expected.</span></span> <span data-ttu-id="557dd-199">這不是衝突。</span><span class="sxs-lookup"><span data-stu-id="557dd-199">This is not a conflict.</span></span>

### <a name="mediation-server"></a><span data-ttu-id="557dd-200">中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="557dd-200">Mediation Server</span></span>

<span data-ttu-id="557dd-201">在 [中繼伺服器]\*\*\*\* 中，指定下列內容：</span><span class="sxs-lookup"><span data-stu-id="557dd-201">In **Mediation Server**, specify the following:</span></span>

- <span data-ttu-id="557dd-p128">如果您要組合中繼伺服器與集區，請選取 [組合的中繼伺服器已啟用]\*\*\*\* 核取方塊。如果選擇不組合中繼伺服器，在此區段中就沒有可用的設定。</span><span class="sxs-lookup"><span data-stu-id="557dd-p128">If you collocate the Mediation Server with the pool, select the **Collocated Mediation Server enabled** check box. If you choose not to collocate the Mediation Server, none of the settings are available in this section.</span></span>

- <span data-ttu-id="557dd-p129">如果您啟用中繼伺服器的組合，便會在集區伺服器上針對傳輸層安全性 (TLS) 定義聆聽連接埠範圍。此連接埠預設為 5067。如果您選取 [啟用 TCP 連接埠]\*\*\*\*，則必須為組合的中繼伺服器定義傳輸控制通訊協定 (TCP) 連接埠。這是選用的設定，您應該參考閘道或 PSTN 需求，來決定是否需要這項設定。TCP 連接埠值預設為 5068。</span><span class="sxs-lookup"><span data-stu-id="557dd-p129">If you enable the collocation of the Mediation Server, define the listening port range on the pool servers for Transport Layer Security (TLS). By default, this port is 5067. If you select **Enable TCP port**, you must define a Transmission Control Protocol (TCP) port for the collocated Mediation Server. This is an optional setting, and you should refer to the requirements of your gateway or PSTN requirements to determine if you need this. By default, the TCP port value is 5068.</span></span>

- <span data-ttu-id="557dd-p130">與組合中繼伺服器相關聯的主幹。如果已經定義主幹，可以將其用來與中繼伺服器相關聯。</span><span class="sxs-lookup"><span data-stu-id="557dd-p130">Trunks that are associated with the collocated Mediation Server. If you have already defined trunks, they will be available to associate with the Mediation Server.</span></span>

- <span data-ttu-id="557dd-p131">如果您有多個主幹與中繼伺服器相關聯，您可以選取閘道，然後按一下 [成為預設]\*\*\*\* 指定預設主幹。若要取消選取成為預設的閘道，請按一下 [取消預設]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="557dd-p131">If you have more than one trunk associated with a Mediation Server, you can specify a default trunk by selecting the gateway and then clicking **Make Default**. To unselect a gateway as the default, click **Unmake Default**.</span></span>

<span data-ttu-id="557dd-213">如需定義和設定前端集區各項設定的詳細資訊，請參閱〈[Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx)〉。</span><span class="sxs-lookup"><span data-stu-id="557dd-213">For details about defining and configuring the settings for the Front End pool, see [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).</span></span>

## <a name="standard-edition-server"></a><span data-ttu-id="557dd-214">Standard Edition Server</span><span class="sxs-lookup"><span data-stu-id="557dd-214">Standard Edition Server</span></span>

<span data-ttu-id="557dd-p132">您可以針對 Standard Edition Server 設定一般、恢復、Web 服務以及中繼伺服器的相關設定。如需詳細資訊，請參閱以下各小節中的資訊。如需定義和設定 Standard Edition Server 設定的詳細資訊，請參閱〈[Defining and Configuring the Topology](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx)〉及〈[Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx)〉。</span><span class="sxs-lookup"><span data-stu-id="557dd-p132">For a Standard Edition server, you can configure general, resiliency, web services, and Mediation Server settings. For details, see the information in the following subsections. For details about defining and configuring the settings for the Standard Edition server, see [Defining and Configuring the Topology](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) and [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).</span></span>

### <a name="general-settings"></a><span data-ttu-id="557dd-218">一般設定</span><span class="sxs-lookup"><span data-stu-id="557dd-218">General Settings</span></span>

<span data-ttu-id="557dd-219">您可以設定下列一般設定：</span><span class="sxs-lookup"><span data-stu-id="557dd-219">You can configure the following general settings:</span></span>

- <span data-ttu-id="557dd-220">**FQDN**。</span><span class="sxs-lookup"><span data-stu-id="557dd-220">**FQDN**.</span></span> <span data-ttu-id="557dd-221">請注意，FQDN 無法變更。</span><span class="sxs-lookup"><span data-stu-id="557dd-221">Note that the FQDN cannot be changed.</span></span> <span data-ttu-id="557dd-222">您必須移除並重新定義 Standard Edition Server，才能變更其相關聯的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="557dd-222">You must remove and redefine the Standard Edition server to change the FQDN associated with it.</span></span>

- <span data-ttu-id="557dd-p134">選取 [使用所有設定的 IP 位址]\*\*\*\* 或 [將服務使用方式限制為選取的 IP 位址]\*\*\*\*。如果您選擇將服務限定於已定義的 IP 位址，則會定義伺服器將用於所有通訊 (PSTN 除外) 的主要 IP 位址。您必須定義個別的 IP 位址供 PSTN 使用。您也可以選取 [啟用 IPv6]\*\*\*\* 為此伺服器啟用 IPv6。</span><span class="sxs-lookup"><span data-stu-id="557dd-p134">Select **Use all configured IP addresses** or to **Limit service usage to selected IP addresses**. If you select to limit the service to defined IP addresses, you will define the Primary IP address that the server will use for all communications, except for PSTN. You define a separate IP address for PSTN usage. You can also select **Enable IPv6** to enable IPv6 for this server.</span></span>

- <span data-ttu-id="557dd-p135">**啟用硬體負載平衡器監控連接埠**。選取核取方塊，然後輸入硬體負載平衡器將用以監控伺服器狀態的連接埠號碼。</span><span class="sxs-lookup"><span data-stu-id="557dd-p135">**Enable Hardware Load Balancer monitoring port**. Select the check box and enter the port number that your Hardware Load Balancer will use to monitor the state of the server.</span></span>

- <span data-ttu-id="557dd-p136">在 [功能]\*\*\*\* 中，定義想要與此伺服器組合的其他角色。您可以設定下列設定：</span><span class="sxs-lookup"><span data-stu-id="557dd-p136">In **Features and Functionality**, define the additional roles that you want to collocate with this server. You can configure the following settings:</span></span>

  - <span data-ttu-id="557dd-p137">**會議**。包含音訊、視訊與應用程式共用。選取此選項後，您可以選取 [電話撥入式 (PSTN) 會議]\*\*\*\*。您可於稍後在 [中繼伺服器] 設定下，指定及定義 PSTN 閘道。</span><span class="sxs-lookup"><span data-stu-id="557dd-p137">**Conferencing**. Includes audio, video and application sharing. After you select this option, you can select **Dial-in (PSTN) conferencing**. You can specify and define a PSTN gateway later under Mediation Server settings.</span></span>

  - <span data-ttu-id="557dd-235">**企業語音**。</span><span class="sxs-lookup"><span data-stu-id="557dd-235">**Enterprise Voice**.</span></span> <span data-ttu-id="557dd-236">在合格的手機和裝置以及商務用 Skype 用戶端啟用內部的語音 over IP 通話。</span><span class="sxs-lookup"><span data-stu-id="557dd-236">Enables internal voice over IP calls to qualified handsets and devices and Skype for Business clients.</span></span> <span data-ttu-id="557dd-237">若要啟用外部通話功能，需要包括中繼伺服器。</span><span class="sxs-lookup"><span data-stu-id="557dd-237">To enable external call capabilities, you need to include a Mediation Server.</span></span> <span data-ttu-id="557dd-238">如需詳細資訊，請參閱本主題稍後的〈中繼伺服器〉。</span><span class="sxs-lookup"><span data-stu-id="557dd-238">For details, see "Mediation Server" later in this topic.</span></span>

- <span data-ttu-id="557dd-239">在 [關聯]\*\*\*\* 中，您可以編輯或指定下列項目：</span><span class="sxs-lookup"><span data-stu-id="557dd-239">In **Associations** you can edit or specify the following:</span></span>

  - <span data-ttu-id="557dd-p139">選取 [SQL Server 儲存區]\*\*\*\* 建立 SQL Server 儲存區與前端伺服器的關聯。您也可以啟用鏡像並選取鏡像見證伺服器。</span><span class="sxs-lookup"><span data-stu-id="557dd-p139">Select **SQL Server store** to associate a SQL Server store with the Front End server. You can also enable mirroring and select a mirroring witness server.</span></span>

  - <span data-ttu-id="557dd-p140">**檔案共用**。修改 Standard Edition Server 所使用的檔案存放區。您可以從先前已定義的檔案存放區中選取一個新的檔案存放區，方式是從清單中加以選取。您可以按一下 [新增]\*\*\*\*，以建立新的檔案存放區。</span><span class="sxs-lookup"><span data-stu-id="557dd-p140">**File share**. Modify the file store that the Standard Edition server is using. You can select a new file store from those already defined by selecting it from the list. You can create a new file store by clicking **New**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="557dd-246">您所指定的伺服器必須存在並加入網域中，您才能發行新定義的拓撲。</span><span class="sxs-lookup"><span data-stu-id="557dd-246">Before publishing the newly defined topology, the server that you specify must exist and be joined to the domain.</span></span>

  - <span data-ttu-id="557dd-p141">**封存**。建立封存 SQL Server 儲存區與 Standard Edition Server 的關聯。您可以從清單中選取伺服器，以選取已定義的封存儲存區，或按一下 [新增]\*\*\*\* 以指定新的封存儲存區。</span><span class="sxs-lookup"><span data-stu-id="557dd-p141">**Archiving**. Associate an Archiving SQL Server store with the Standard Edition server. You can select from an already defined Archiving store by selecting the server from the list, or click **New** to specify a new Archiving store.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="557dd-250">您所指定的伺服器必須存在並加入網域中，您才能發行新定義的拓撲。</span><span class="sxs-lookup"><span data-stu-id="557dd-250">Before publishing the newly defined topology, the server that you specify must exist and be joined to the domain.</span></span>

  - <span data-ttu-id="557dd-p142">**監控 (CDR 和 QoE 計量)**。建立監控 SQL Server 儲存區與 Standard Edition Server 的關聯。您可以從清單中選取伺服器，以選取已定義的監控伺服器，或按一下 [新增]\*\*\*\* 以指定新的監控伺服器。</span><span class="sxs-lookup"><span data-stu-id="557dd-p142">**Monitoring (CDR and QoE metrics**. Associate a Monitoring SQL Server store with the Standard Edition server. You can select from an already defined Monitoring Server by selecting the server from the list, or click **New** to specify a new Monitoring Server.</span></span>

  - <span data-ttu-id="557dd-p143">**建立集區與 Office Web Apps Server 的關聯**。選取這個選項可建立 Office Web Apps Server 與前端集區的關聯。從清單中選取現有的伺服器，或按一下 [新增]\*\*\*\* 建立新的 Office Web Apps Server。</span><span class="sxs-lookup"><span data-stu-id="557dd-p143">**Associate pool with an Office Web Apps Server**. Select this option to associate an Office Web Apps Server with the Front End pool. Select an existing server from the list, or click **New** to create a new Office Web Apps Server.</span></span>

  - <span data-ttu-id="557dd-p144">**建立 Edge 集區的關聯**。建立 Edge Server 或集區與 Standard Edition Server 的關聯。您可以從清單中選取伺服器，以選取已定義的 Edge Server 或集區，或按一下 [新增]\*\*\*\* 以指定新的 Edge Server 或集區。</span><span class="sxs-lookup"><span data-stu-id="557dd-p144">**Associate Edge pool**. Associate an Edge Server or pool with the Standard Edition server. You can select from an already defined Edge Server or pool by selecting the server from the list, or click **New** to specify a new Edge Server or pool.</span></span>

### <a name="resiliency"></a><span data-ttu-id="557dd-260">恢復</span><span class="sxs-lookup"><span data-stu-id="557dd-260">Resiliency</span></span>

<span data-ttu-id="557dd-p145">恢復功能提供伺服器的嚴重損壞修復和高可用性。藉由提供備份，如果主要伺服器失敗，則備份可以接管，讓使用者能夠進行登入和通訊。視同時失敗的系統而定，使用者可用的功能可能會減少。</span><span class="sxs-lookup"><span data-stu-id="557dd-p145">Resiliency provides disaster recovery and high availability for the server. By providing a backup, if the primary server fails, the backup can take over, enabling users to sign in and communicate. It is possible that there will be reduced functionality for users, depending on what systems have also failed.</span></span>

<span data-ttu-id="557dd-p146">從清單中選取將作為伺服器之備份的前端集區或 Standard Edition Server。您也可以選擇啟用「容錯移轉」與「容錯回復」時間間隔。啟用容錯移轉與容錯回復時間設定 (以秒為單位來指定) 可自動偵測失敗的登錄器，並且有容錯回復時間可自動判定是否已備份主要登錄器。</span><span class="sxs-lookup"><span data-stu-id="557dd-p146">From the list, select the Front End pool or Standard Edition server that will act as the backup for the server. You can also select to enable Failover and Fallback time intervals. Enabling the failover and fallback time settings (specified in seconds) enables automatic detection of a failed Registrar, and a fallback time to allow for automatic determination that the primary is back up.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="557dd-p147">定義失敗偵測和容錯回復間隔時，請小心不要讓輸入的間隔導致在伺服器短時間無法回應時，發生容錯移轉和容錯回復。根據集區或伺服器的載入情形，主要伺服器可能會在短時間內無法回應。「集區對集區」或「集區對 Standard Edition Server」的容錯移轉與容錯回復預設值，分別為 300 秒與 600 秒。從網站中的 Survivable Branch Appliance 或 Survivable Branch 伺服器到集區或 Standard Edition Server，容錯移轉的預設值為 120 秒，容錯回復的預設值為 240 秒。</span><span class="sxs-lookup"><span data-stu-id="557dd-p147">When defining the Failure detection and the Fallback interval, you should be careful not to enter an interval that will cause the failover and fallback to occur if the server should fail to respond for a short period of time. It is possible that the primary server may not respond for short periods of time, based on the loading of the pool or servers. The default values for the failover and fallback are 300 seconds and 600 seconds for pool to pool, or pool to Standard Edition server. In the event of a Survivable Branch Appliance or a Survivable Branch Server in a site to a pool or Standard Edition server, the default values are 120 seconds for failover and 240 seconds for fallback.</span></span>

### <a name="web-services"></a><span data-ttu-id="557dd-271">Web 服務</span><span class="sxs-lookup"><span data-stu-id="557dd-271">Web Services</span></span>

<span data-ttu-id="557dd-272">若要為伺服器上的 Web 服務編輯或指定其他設定，請修改或指定 [內部 Web 服務]\*\*\*\* 與 [外部 Web 服務]\*\*\*\* 中的設定。</span><span class="sxs-lookup"><span data-stu-id="557dd-272">To edit or specify additional setting for the web services on the server, modify or specify settings in **Internal Web services** and **External Web services**.</span></span>

<span data-ttu-id="557dd-273">針對 [內部 Web 服務]\*\*\*\*，您可以指定下列項目：</span><span class="sxs-lookup"><span data-stu-id="557dd-273">For **Internal Web services**, you can specify the following:</span></span>

- <span data-ttu-id="557dd-p148">如果您選取 [覆寫 FQDN]，您可以為伺服器上的內部 Web 服務識別指定不同的 FQDN。根據預設，此設定是為 Standard Edition Server 定義的現行伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="557dd-p148">If you select Override FQDN, you can specify a different FQDN for the Internal Web services identity on the server. By default, the setting is the current server name as defined for the Standard Edition server.</span></span>

- <span data-ttu-id="557dd-p149">部署所需的 HTTP 與 HTTPS 之聆聽連接埠與發行的連接埠。最常見的設定是讓 HTTP 使用預設設定連接埠 80，讓 HTTPS 使用預設設定連接埠 443，且除非您的組織與基礎結構設計有特定需求，否則通常不需加以變更。</span><span class="sxs-lookup"><span data-stu-id="557dd-p149">Listening and published ports for HTTP and HTTPS that your deployment requires. The default setting of port 80 for HTTP and port 443 for HTTPS are the most common settings, and typically do not need to be changed unless you have specific requirements within your organization and infrastructure design.</span></span>

<span data-ttu-id="557dd-278">針對 [外部 Web 服務]\*\*\*\*，您可以指定下列項目：</span><span class="sxs-lookup"><span data-stu-id="557dd-278">For **External Web services**, you can specify the following:</span></span>

- <span data-ttu-id="557dd-p150">外部 Web 服務的 FQDN。此處指定的 FQDN 通常會依您外部連線的需求 (例如反向 Proxy) 而定義。</span><span class="sxs-lookup"><span data-stu-id="557dd-p150">The FQDN of the External Web services. The FQDN specified here will usually be defined by the requirements of your external connection requirements, such as the reverse proxy.</span></span>

- <span data-ttu-id="557dd-p151">部署所需之 HTTP 與 HTTPS 的聆聽連接埠。針對 HTTP 和 HTTPS，最初定義的預設設定分別為連接埠 8080 和連接埠 4443。您可以根據您反向 Proxy 與外部網路的需求，為聆聽連接埠變更這些設定。這些值將決定伺服器會聆聽哪些連接埠的傳入要求。這些值通常無需變更，除非伺服器上的連接埠需求有所衝突。</span><span class="sxs-lookup"><span data-stu-id="557dd-p151">Listening ports for HTTP and HTTPS that your deployment requires. The default setting of port 8080 for HTTP and port 4443 for HTTPS is defined initially. You change these settings for the listening ports based on what the requirements are for your reverse proxy and external network requirements. These values determine what ports the server will listen for incoming requests. Typically, these do not need to be changed, unless there is conflict of port requirements on the server.</span></span>

### <a name="mediation-server"></a><span data-ttu-id="557dd-286">中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="557dd-286">Mediation Server</span></span>

<span data-ttu-id="557dd-287">針對 [中繼伺服器]\*\*\*\*，您可以指定下列內容：</span><span class="sxs-lookup"><span data-stu-id="557dd-287">For **Mediation Server**, you can specify the following:</span></span>

- <span data-ttu-id="557dd-p152">如果您要組合中繼伺服器與伺服器，請選取 [組合的中繼伺服器已啟用]\*\*\*\* 核取方塊。如果選擇不組合中繼伺服器，在此區段中就沒有可用的設定。</span><span class="sxs-lookup"><span data-stu-id="557dd-p152">If you collocate the Mediation Server with the server, select the check box **Collocated Mediation Server enabled**. If you choose not to collocate the Mediation Server, none of the settings are available in this section.</span></span>

- <span data-ttu-id="557dd-p153">如果您已啟用中繼伺服器的組合，便會在伺服器上針對 TLS 定義聆聽連接埠範圍。此連接埠預設為 5067。如果您選取 [啟用 TCP 連接埠]\*\*\*\*，則必須為組合的中繼伺服器定義 TCP 連接埠。這是選用的設定，您應該參考閘道或 PSTN 需求，來決定是否需要這項設定。TCP 連接埠值預設為 5068。</span><span class="sxs-lookup"><span data-stu-id="557dd-p153">If you have enabled the collocation of the Mediation Server, you define the listening port range on the server for TLS. By default, this port is 5067. If you select **Enable TCP port**, you must define a TCP port for the collocated Mediation Server. This is an optional setting, and you should refer to the requirements of your gateway or PSTN requirements to determine if you need this. By default, the TCP port value is 5068.</span></span>

- <span data-ttu-id="557dd-p154">與組合中繼伺服器相關聯的主幹。如果已經定義主幹，可以將其用來與中繼伺服器相關聯。</span><span class="sxs-lookup"><span data-stu-id="557dd-p154">Trunks that are associated with the collocated Mediation Server. If you have already defined trunks, they will be available to associate with the Mediation Server.</span></span>

- <span data-ttu-id="557dd-p155">如果您有多個閘道與中繼伺服器相關聯，您可以選取閘道，然後按一下 [成為預設]\*\*\*\* 指定預設閘道。若要取消選取成為預設的閘道，請按一下 [取消預設]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="557dd-p155">If you have more than one gateway associated with a Mediation Server, you can specify a default gateway by selecting the gateway and then clicking **Make Default**. To unselect a gateway as the default, click **Unmake Default**.</span></span>

<span data-ttu-id="557dd-299">如需定義和設定 Standard Edition Server 設定的詳細資訊，請參閱〈[Defining and Configuring the Topology](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx)〉及〈[Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx)〉。</span><span class="sxs-lookup"><span data-stu-id="557dd-299">For details about defining and configuring the settings for the Standard Edition server, see [Defining and Configuring the Topology](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) and [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).</span></span>


