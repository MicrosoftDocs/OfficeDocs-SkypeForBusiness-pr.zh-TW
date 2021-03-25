---
title: 前端一般設定展開工具 (適用於 Lync Server 2010)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.FrontEndGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58269c38-98d9-499f-ab69-6a63a6e5530e
description: 您可以編輯或設定下列屬性，以編輯前端伺服器或前端集區的屬性。 設定頁面可分成下列區段：
ms.openlocfilehash: 63c784cbd254decdb108d8d8408cd01ef44657a8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118622"
---
# <a name="front-end-general-settings-expander-for-lync-server-2010"></a><span data-ttu-id="04ab5-104">前端一般設定展開工具 (適用於 Lync Server 2010)</span><span class="sxs-lookup"><span data-stu-id="04ab5-104">Front End General Settings Expander for Lync Server 2010</span></span>

<span data-ttu-id="04ab5-105">您可以編輯或設定下列屬性，以編輯前端伺服器或前端集區的屬性。</span><span class="sxs-lookup"><span data-stu-id="04ab5-105">You edit the properties of the Front End Server or Front End pool by editing or configuring the following attributes.</span></span> <span data-ttu-id="04ab5-106">設定頁面可分成下列區段：</span><span class="sxs-lookup"><span data-stu-id="04ab5-106">The configuration page is separated into the following sections:</span></span>

 <span data-ttu-id="04ab5-107">**一般**</span><span class="sxs-lookup"><span data-stu-id="04ab5-107">**General**</span></span>

- <span data-ttu-id="04ab5-108">**FQDN**：前端伺服器或前端集區的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="04ab5-108">**FQDN**: The fully qualified domain name of the Front End Server or Front End pool.</span></span>

- <span data-ttu-id="04ab5-109">選取 [ **使用所有設定的 IP 位址** ]，以使用前端伺服器或前端集區上設定的所有位址。</span><span class="sxs-lookup"><span data-stu-id="04ab5-109">Select **Use all configured IP addresses** to make use of all addresses configured on Front End Server or Front End pool.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="04ab5-110">如果您組合前端伺服器或前端集區上的轉送伺服器，請勿選取此選項。</span><span class="sxs-lookup"><span data-stu-id="04ab5-110">You should not select this option if you collocate the Mediation Server on the Front End Server or Front End pool.</span></span> <span data-ttu-id="04ab5-111">轉送伺服器和前端伺服器需要專用的 IP 位址，以進行通訊。</span><span class="sxs-lookup"><span data-stu-id="04ab5-111">Mediation Servers and Front End Servers need dedicated IP addresses on which to communicate.</span></span>

- <span data-ttu-id="04ab5-112">選取 [ **將服務使用方式限制為選取的 IP 位址** ]，然後輸入前端伺服器或前端集區的 ip 位址， **以用於與** 其他部署的通訊。</span><span class="sxs-lookup"><span data-stu-id="04ab5-112">Select **Limit service usage to selected IP addresses** and enter the IP address for **Primary IP address** for the Front End Server or Front End pool communication with the rest of the deployment.</span></span> <span data-ttu-id="04ab5-113">輸入 **PSTN ip 位址** 與轉送伺服器相關聯的 ip 位址。</span><span class="sxs-lookup"><span data-stu-id="04ab5-113">Type in **PSTN IP address** the IP address that is associated with the Mediation Server.</span></span>

    <span data-ttu-id="04ab5-114">**功能**</span><span class="sxs-lookup"><span data-stu-id="04ab5-114">**Features and functionality**</span></span>

- <span data-ttu-id="04ab5-115">**會議**：如果部署需要會議功能，請選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="04ab5-115">**Conferencing**: Select the check box if you want conferencing features in your deployment.</span></span> <span data-ttu-id="04ab5-116">會議功能包含音訊、視訊、應用程式共用、桌面共用及 Web 會議。</span><span class="sxs-lookup"><span data-stu-id="04ab5-116">Conferencing includes audio, video, application sharing, desktop sharing, and Web conferencing.</span></span> <span data-ttu-id="04ab5-117">您將需要為此屬性頁面稍後) 中所定義的 Web 會議 (建立和關聯 [Office Web Apps Server]。</span><span class="sxs-lookup"><span data-stu-id="04ab5-117">You will need to create and associate an Office Web Apps Server for Web conferencing (defined later in this Properties page).</span></span>

- <span data-ttu-id="04ab5-118">如果選取會議，則可以選取 [電話撥入式 (PSTN) 會議]。</span><span class="sxs-lookup"><span data-stu-id="04ab5-118">If you selected Conferencing, **Dial-in (PSTN) conferencing** can be selected.</span></span> <span data-ttu-id="04ab5-119">選取此核取方塊可啟用電話撥入式會議功能。</span><span class="sxs-lookup"><span data-stu-id="04ab5-119">Select the check box to enable dial-in conferencing features.</span></span>

- <span data-ttu-id="04ab5-120">如果您想要部署功能，以讓 Lync Server 2013 成為使用語音 over IP (的電話語音系統，請選取 [ **企業語音** ] 核取方塊。 VoIP) 技術，包括使用轉送伺服器、PSTN 閘道及 IP-PBX （結合或獨立）根據設計和需求來部署話筒電話、SIP 主幹或公用交換電話網路 connectivity 的選項。</span><span class="sxs-lookup"><span data-stu-id="04ab5-120">Select the check box **Enterprise Voice** if you intend to deploy features to enable Lync Server 2013 to act as your telephone voice system using voice over IP (VoIP) technologies, including the option of deploying handset telephones, SIP trunks, or public switched telephone network connectivity using Mediation Server, PSTN Gateways, and IP-PBX, in combination or alone, based on the design and requirements.</span></span> <span data-ttu-id="04ab5-121">如需有關 Enterprise Voice 的詳細資訊，請參閱[商務用 Skype Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)的[Enterprise voice](/previous-versions/office/lync-server-2013/lync-server-2013-enterprise-voice) And Plan for enterprise voice。</span><span class="sxs-lookup"><span data-stu-id="04ab5-121">For detail on Enterprise Voice, see [Enterprise Voice](/previous-versions/office/lync-server-2013/lync-server-2013-enterprise-voice) and [Plan for Enterprise Voice in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)</span></span>

    <span data-ttu-id="04ab5-122">**協會**</span><span class="sxs-lookup"><span data-stu-id="04ab5-122">**Associations**</span></span>

- <span data-ttu-id="04ab5-123">**Sql server 儲存區**： sql SERVER 的 FQDN (，並選擇性地) 與前端伺服器或前端集區相關聯的命名實例。</span><span class="sxs-lookup"><span data-stu-id="04ab5-123">**SQL Server store**: The FQDN of the SQL Server (and optionally a named instance) associated with the Front End Server or Front End pool.</span></span> <span data-ttu-id="04ab5-124">您可以從清單中選取 SQL Server 儲存區，或按一下 [新增] 建立新的 SQL Server 儲存區</span><span class="sxs-lookup"><span data-stu-id="04ab5-124">You select the SQL Server store from the list or you create a new SQL Server store by clicking **New**</span></span>

- <span data-ttu-id="04ab5-125">檔案 **存放區**：在 [格式]) 中，選取 `\\<FQDN of server>\<share name>` 將充當 Lync server 2013 為複寫、會議目錄及其他用途建立及使用之共用檔案的檔案存放區位置的格式中的 [伺服器和共用 (的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="04ab5-125">**File store**: You select the FQDN of the server and the share (in the format  `\\<FQDN of server>\<share name>`) that will act as the file store location for the shared files that Lync Server 2013 creates and uses for replication, conference directories, and other purposes.</span></span> <span data-ttu-id="04ab5-126">您可以從清單中選取檔案存放區，或按一下 [新增] 建立新的檔案存放區。</span><span class="sxs-lookup"><span data-stu-id="04ab5-126">You select the File store from the list or you create a new File store by clicking **New**.</span></span>

- <span data-ttu-id="04ab5-127">選取 [ **關聯封存伺服器** ] 核取方塊，啟用此前端伺服器或前端集區的封存伺服器。</span><span class="sxs-lookup"><span data-stu-id="04ab5-127">Select the **Associate Archiving Server** checkbox to enable an Archiving Server for this Front End Server or Front End pool.</span></span> <span data-ttu-id="04ab5-128">選取此核取方塊後，請從清單中選取現有的封存伺服器，或按一下 [ **新增** ] 建立新封存伺服器的定義。</span><span class="sxs-lookup"><span data-stu-id="04ab5-128">After selecting the check box, you select an existing Archiving Server from the list or click **New** to create the definitions for a new Archiving Server.</span></span>

- <span data-ttu-id="04ab5-129">選取 [ **關聯監控伺服器** ] 核取方塊，啟用此前端伺服器或前端集區的監控伺服器。</span><span class="sxs-lookup"><span data-stu-id="04ab5-129">Select the **Associate Monitoring Server** checkbox to enable a Monitoring Server for this Front End Server or Front End pool.</span></span> <span data-ttu-id="04ab5-130">選取此核取方塊後，請從清單中選取現有的監控伺服器，或按一下 [ **新增** ] 建立新監控伺服器的定義。</span><span class="sxs-lookup"><span data-stu-id="04ab5-130">After selecting the check box, you select an existing Monitoring Server from the list or click **New** to create the definitions for a new Monitoring Server.</span></span>

- <span data-ttu-id="04ab5-131">選取 [ **關聯媒體元件的 Edge 集區 (** ] 核取方塊，以啟用此前端伺服器或前端集區的 edge Server。</span><span class="sxs-lookup"><span data-stu-id="04ab5-131">Select the **Associate Edge Pool (for media components** checkbox to enable an Edge Server for this Front End Server or Front End pool.</span></span> <span data-ttu-id="04ab5-132">選取此核取方塊之後，您可以從清單中選取現有的 Edge Server 或集區，或按一下 [ **新增** ] 建立新 Edge Server 或集區的定義。</span><span class="sxs-lookup"><span data-stu-id="04ab5-132">After selecting the check box, you select an existing Edge Server or pool from the list or click **New** to create the definitions for a new Edge Server or pool.</span></span>

  <span data-ttu-id="04ab5-133">**彈性**</span><span class="sxs-lookup"><span data-stu-id="04ab5-133">**Resiliency**</span></span>

- <span data-ttu-id="04ab5-134">選取 [ **關聯的備份註冊區集** 區] 核取方塊，以從清單中選取要作為備份 ( 報名者的前端伺服器或前端集區，也就是在主要失敗的情況下，會將前端伺服器或前端集區指定為次要註冊機) </span><span class="sxs-lookup"><span data-stu-id="04ab5-134">Select the **Associated backup Registrar pool** check box to select from the list a Front End Server or Front End pool that will be the backup Registrar ( that is, the Front End Server or Front End pool designated as a secondary registrar in the event that the primary fails)</span></span>

- <span data-ttu-id="04ab5-135">選取 [關聯的備份登錄器集區] 並選擇備份登錄器之後，即可選取 [語音的自動容錯移轉和容錯回復]。</span><span class="sxs-lookup"><span data-stu-id="04ab5-135">If you selected Associated backup Registrar pool and have chosen a backup registrar, you can select the checkbox for **Automatic failover and failback for Voice**.</span></span> <span data-ttu-id="04ab5-136">您現在可以定義 [語音失敗偵測間隔 (秒)] 和 [語音容錯回復間隔 (秒)] 的數值屬性。</span><span class="sxs-lookup"><span data-stu-id="04ab5-136">You can now define numerical properties for **Voice failover detection internal (sec)** and **Voice failback interval (sec)**.</span></span> <span data-ttu-id="04ab5-137">如需詳細資訊，請參閱＜[Planning for Enterprise Voice Resiliency](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-enterprise-voice-resiliency)＞</span><span class="sxs-lookup"><span data-stu-id="04ab5-137">For details, see [Planning for Enterprise Voice Resiliency](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-enterprise-voice-resiliency)</span></span>

  <span data-ttu-id="04ab5-138">**Web 服務**</span><span class="sxs-lookup"><span data-stu-id="04ab5-138">**Web services**</span></span>

- <span data-ttu-id="04ab5-p114">若要設定 [內部 Web 服務]，您可以為 [HTTP] 和 [HTTPS] 定義 [聆聽連接埠]。預設值分別為 TCP 連接埠 80 和 TCP 連接埠 443。您也可以為 [HTTP] 和 [HTTPS] 設定 [發行的連接埠]。預設值分別為 TCP 連接埠 80 和 TCP 連接埠 443。請根據您的內部 Web 服務設定及負載平衡器的用途 (硬體負載平衡器和 DNS 負載平衡) 來調整連接埠值，以定義聆聽連接埠和發行的連接埠。</span><span class="sxs-lookup"><span data-stu-id="04ab5-p114">To configure **Internal web services**, you define **Listening ports** for **HTTP** and **HTTPS**. By default, these are TCP port 80 and TCP port 443, respectively. You also configure the **Published ports** for **HTTP** and **HTTPS**. By default, these are TCP port 80 and TCP port 443, respectively. Based on your internal web services configuration and use of load balancers (hardware load balancers and DNS load balancing), adjust the port values to define the listening and published ports.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="04ab5-p115">內部 Web 服務以及已定義的聆聽連接埠和發行的連接埠，適用於內部用戶端和裝置。外部用戶端和裝置使用外部 Web 服務聆聽連接埠和發行的連接埠，以及已定義的外部 Web 服務完整網域名稱 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="04ab5-p115">Internal web services and the defined listening and published ports are for internal clients and devices. External clients and devices use the external web services listening and published ports, along with the defined external web services fully qualified domain name (FQDN).</span></span>

- <span data-ttu-id="04ab5-p116">若要設定 [外部 Web 服務]，您可以為 [HTTP] 和 [HTTPS] 定義 [聆聽連接埠]。預設值分別為 TCP 連接埠 80 和 TCP 連接埠 443。您也可以為 [HTTP] 和 [HTTPS] 設定 [發行的連接埠]。預設值分別為 TCP 連接埠 80 和 TCP 連接埠 443。請根據您的內部 Web 服務設定及負載平衡器的用途 (硬體負載平衡器和 DNS 負載平衡) 來調整連接埠值，以定義聆聽連接埠和發行的連接埠。</span><span class="sxs-lookup"><span data-stu-id="04ab5-p116">To configure **External web services**, you define **Listening ports** for **HTTP** and **HTTPS**. By default, these are TCP port 80 and TCP port 443, respectively. You also configure the **Published ports** for **HTTP** and **HTTPS**. By default, these are TCP port 80 and TCP port 443, respectively. Based on your internal web services configuration and use of load balancers (hardware load balancers and DNS load balancing), adjust the port values to define the listening and published ports.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="04ab5-151">外部 Web 服務以及已定義的聆聽連接埠和發行的連接埠，適用於外部用戶端和裝置。</span><span class="sxs-lookup"><span data-stu-id="04ab5-151">External web services and the defined listening and published ports are for external clients and devices.</span></span> <span data-ttu-id="04ab5-152">外部用戶端和裝置使用外部 Web 服務聆聽連接埠和發行的連接埠 (一般會由反向 Proxy 及已定義的外部 Web 服務完整網域名稱 (FQDN) 所定義)。</span><span class="sxs-lookup"><span data-stu-id="04ab5-152">External clients and devices use the external web services listening and published ports, typically defined by your reverse proxy along with the defined external web services fully qualified domain name (FQDN).</span></span> <span data-ttu-id="04ab5-153">外部 Web 服務 FQDN 與「簡單 URL」的關聯可定義統一資源定位器 (URL) 位址，以供外部用戶端用來存取外部使用者和裝置的可用服務。</span><span class="sxs-lookup"><span data-stu-id="04ab5-153">The relationship of the external web services FQDN and the Simple URLs define the uniform resource locator (URL) addresses that external clients will use to access services available for external users and devices.</span></span> <span data-ttu-id="04ab5-154">如需簡單 URL 的詳細資訊，請參閱＜[Planning for Simple URLs](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-simple-urls)＞。</span><span class="sxs-lookup"><span data-stu-id="04ab5-154">For more details on Simple URLs, see [Planning for Simple URLs](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-simple-urls).</span></span>

  <span data-ttu-id="04ab5-155">**中繼伺服器**</span><span class="sxs-lookup"><span data-stu-id="04ab5-155">**Mediation Server**</span></span>

- <span data-ttu-id="04ab5-156">若要設定組合轉送伺服器的中繼 **伺服器** 屬性 (也就是說，在前端伺服器或前端集區上部署的轉送伺服器) ，請選取 [ **組合轉送伺服器已啟用**]。</span><span class="sxs-lookup"><span data-stu-id="04ab5-156">To configure **Mediation Server** properties for a collocated Mediation Server (that is, a Mediation Server deployed on the Front End Server or Front End pool), select **Collocated Mediation server enabled**.</span></span>

- <span data-ttu-id="04ab5-157">若要定義組合轉送伺服器的 **聆聽埠** ，請輸入組合轉送伺服器正在接聽的 **TLS** 和 **TCP** 埠值。</span><span class="sxs-lookup"><span data-stu-id="04ab5-157">To define the **Listening ports** for a collocated Mediation Server, you type the **TLS** and **TCP** port value that the collocated Mediation Server is listening on.</span></span> <span data-ttu-id="04ab5-158">根據預設，TLS 會定義為 TCP 連接埠 5067。</span><span class="sxs-lookup"><span data-stu-id="04ab5-158">By default, TLS is defined as TCP port 5067.</span></span>

- <span data-ttu-id="04ab5-159">若要定義轉送伺服器的 TCP 通訊埠值，請選取 [ **啟用 TCP 埠** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="04ab5-159">To define a TCP port value for the Mediation Server, you select the **Enable TCP port** check box.</span></span> <span data-ttu-id="04ab5-160">根據預設，轉送伺服器會透過 TCP 通訊協定使用傳輸層安全性 (TLS) 。</span><span class="sxs-lookup"><span data-stu-id="04ab5-160">By default, the Mediation Server uses the transport layer security (TLS) over TCP protocol.</span></span> <span data-ttu-id="04ab5-161">只有啟用 [啟用 TCP 連接埠] 選項時，才可以使用 TCP 連接埠。</span><span class="sxs-lookup"><span data-stu-id="04ab5-161">TCP ports are available only when the Enable TCP Port selection is enabled.</span></span>

    > [!NOTE]
    > <span data-ttu-id="04ab5-p120">這是選用設定，您應該參考閘道或 PSTN 需求，來決定是否需要這項設定。TCP 連接埠值預設為 5068。</span><span class="sxs-lookup"><span data-stu-id="04ab5-p120">This is an optional setting, and you should refer to the requirements of your gateway or PSTN to determine if you need this. By default, the TCP port value is 5068.</span></span>

- <span data-ttu-id="04ab5-p121">您定義與組合中繼伺服器相關聯的主幹。如果已經定義主幹，可以將其用來與中繼伺服器相關聯。</span><span class="sxs-lookup"><span data-stu-id="04ab5-p121">You define trunks that are associated with the collocated Mediation Server. If you have already defined trunks, they will be available to associate with the Mediation Server.</span></span>

    <span data-ttu-id="04ab5-166">如果您有多個閘道與轉送伺服器相關聯，您可以選取要設為預設的閘道，然後按一下 [ **成為預設**]，以指定預設閘道。</span><span class="sxs-lookup"><span data-stu-id="04ab5-166">If you have more than one gateway associated with a Mediation Server, you can specify the default gateway by selecting the gateway that you want to make the default, and clicking **Make Default**.</span></span> <span data-ttu-id="04ab5-167">如果選擇移除目前的預設閘道，請選取閘道，然後按一下 [取消預設]。</span><span class="sxs-lookup"><span data-stu-id="04ab5-167">If you choose to remove the current default gateway, select the gateway and click **Unmake Default**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="04ab5-168">如果您變更此對話方塊中的屬性，您必須在所有受影響的伺服器上發行拓撲，並執行商務用 Skype Server 部署嚮導。</span><span class="sxs-lookup"><span data-stu-id="04ab5-168">If you make changes to the properties in this dialog, you must publish the topology and run the Skype for Business Server Deployment Wizard on all affected servers.</span></span> <span data-ttu-id="04ab5-169">在發佈新的拓撲之後，必須執行「商務用 Skype 伺服器部署」嚮導所受影響的伺服器清單，以成為成功拓撲發行摘要畫面上的連結。</span><span class="sxs-lookup"><span data-stu-id="04ab5-169">After publishing the new topology, a list of affected servers where the Skype for Business Server Deployment Wizard must be run is provided for you as a link on the successful topology publishing summary screen.</span></span> <span data-ttu-id="04ab5-170">如需發行已更新之拓撲的詳細資訊，請參閱＜[Publish the Topology](/previous-versions/office/lync-server-2013/lync-server-2013-publish-the-topology)＞。</span><span class="sxs-lookup"><span data-stu-id="04ab5-170">For details on publishing the updated topology, see [Publish the Topology](/previous-versions/office/lync-server-2013/lync-server-2013-publish-the-topology).</span></span> <span data-ttu-id="04ab5-171">如需商務用 Skype Server 部署嚮導的詳細資訊，請參閱 [Lync Server 系統管理工具](/previous-versions/office/lync-server-2013/lync-server-2013-lync-server-administrative-tools)。</span><span class="sxs-lookup"><span data-stu-id="04ab5-171">For details on the Skype for Business Server Deployment Wizard , see [Lync Server Administrative Tools](/previous-versions/office/lync-server-2013/lync-server-2013-lync-server-administrative-tools).</span></span>

<span data-ttu-id="04ab5-172">按一下 [確定] 儲存並認可拓撲文件的變更。</span><span class="sxs-lookup"><span data-stu-id="04ab5-172">Click **OK** to save and commit your changes to the topology document.</span></span>

<span data-ttu-id="04ab5-173">按一下 [ **取消** ] 捨棄您的變更，並關閉前端伺服器或前端集區的 **Edit 屬性** 。</span><span class="sxs-lookup"><span data-stu-id="04ab5-173">Click **Cancel** to discard your changes and close the **Edit Properties** for the Front End Server or Front End pool.</span></span>

<span data-ttu-id="04ab5-174">按一下 [說明] 閱讀此說明主題。</span><span class="sxs-lookup"><span data-stu-id="04ab5-174">Click **Help** to read this help topic.</span></span>

## <a name="see-also"></a><span data-ttu-id="04ab5-175">另請參閱</span><span class="sxs-lookup"><span data-stu-id="04ab5-175">See also</span></span>

[<span data-ttu-id="04ab5-176">定義及設定前端集區或 Standard Edition Server</span><span class="sxs-lookup"><span data-stu-id="04ab5-176">Define and Configure a Front End Pool or Standard Edition Server</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server)