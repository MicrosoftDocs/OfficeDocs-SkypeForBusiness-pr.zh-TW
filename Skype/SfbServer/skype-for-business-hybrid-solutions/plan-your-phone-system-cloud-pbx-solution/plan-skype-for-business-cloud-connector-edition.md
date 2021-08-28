---
title: 規劃商務用 Skype Cloud Connector Edition
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 6ce0e580-8c4a-45de-a54f-e39e438335d6
description: 在商務用 Skype Cloud Connector Edition 上尋找一組封裝虛擬機器，以 (vm) 執行內部部署 PSTN 連線與電話系統 (Cloud PBX) 。
ms.openlocfilehash: 65e1d78a894b967391f44d6859c7fe50f42a7145
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58628455"
---
# <a name="plan-for-skype-for-business-cloud-connector-edition"></a>規劃商務用 Skype Cloud Connector Edition

> [!Important]
> 雲端連接器 Edition 會在2021年7月31日和商務用 Skype 線上時終止。 當您的組織升級至 Teams 後，請瞭解如何使用[直接路由](/MicrosoftTeams/direct-routing-landing-page)將您的內部部署電話網絡連線至 Teams。

在商務用 Skype Cloud Connector Edition 上尋找一組封裝虛擬機器，以 (vm) 執行內部部署 PSTN 連線與電話系統 (Cloud PBX) 。

如果您沒有現有的 Lync Server 或商務用 Skype Server 部署，Cloud Connector Edition 可能是您組織的適當解決方案。 如果您仍在調查哪一電話系統解決方案適合您的企業，請參閱[Microsoft 電話語音解決方案](/microsoftteams/cloud-voice-landing-page)。

這份檔描述 Cloud Connector Edition 需求和支援的拓撲，並協助您規劃雲端連接器 Edition 部署。 在您設定雲端連接器環境之前，請務必閱讀本文。 當您準備好部署及設定 Cloud Connector Edition 時，請參閱[configure and manage 商務用 Skype Cloud Connector Edition](configure-skype-for-business-cloud-connector-edition.md)。

現在可以使用雲端連接器 Edition 2.1。 若尚未升級至2.1，請參閱 [升級至新版本的雲端連接器](upgrade-to-a-new-version-of-cloud-connector.md)。 您可以在中找到安裝檔 [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) 。

> [!NOTE]
> 在發行新版本之後，Microsoft 支援舊版的雲端連接器 Edition，版本為60天。 在2.1 發行後，Microsoft 會在60天內支援版本2.0.1，以供您升級時間。 已不再支援2.0.1 之前的所有版本。

Cloud Connector Edition 是一組混合式服務，包含一組封裝式虛擬機器 (Vm) ，可搭配電話系統執行內部部署 PSTN 連線。 在虛擬化環境中部署最低的商務用 Skype Server 拓撲，您組織中位於雲端的使用者可以從 Microsoft 雲端接收 PBX 服務，但是 PSTN 連線是透過現有的內部部署語音基礎結構提供的。

![拓撲圖，顯示將雲端 pbx 連接至內部部署商務用 Skype 的雲端 pbx 閘道。](../../media/bd898e69-6458-4276-aebe-1854f28ed6fa.png)

因為 Cloud Connector 可讓您將電話系統服務與現有的電話語音環境（例如，PBX、類比裝置及通話中心）整合，所以您可以從現有的電話語音解決方案中執行分階段遷移，以電話系統。

例如，假設您的公司有複雜的話務中心，其特定功能電話系統未提供。 您可以選擇讓話務中心使用者保留現有的解決方案，但將其他使用者移至電話系統。

雲端連接器會提供位於內部部署和線上之使用者之間的路由，您可以選擇搭配使用您自己的 PSTN 提供者與電話系統。

規劃雲端連接器版本部署時，請考慮下列事項：

- 若要使用雲端連接器以利用雲端語音方案，您必須註冊包含電話系統的 Microsoft 365 或 Office 365 組織。 如果您尚無 Microsoft 365 或 Office 365 組織，您可以瞭解如何註冊： [Microsoft 365 商務](https://products.office.com/business/office)。 請注意，您需要註冊包括商務用 Skype 線上的計畫。

- 若要使用商務用 Skype 線上服務註冊雲端連接器裝置，並執行各種 Cmdlet，Cloud connector 2.0 和更新版本需要具有商務用 Skype 承租人系統管理員許可權的專屬 Microsoft 365 或 Office 365 帳戶。 2.0 之前的雲端連接器版本必須具有租使用者全域管理員許可權的專屬 Microsoft 365 或 Office 365 帳戶。

- 雲端連接器不需要完整內部部署商務用 Skype Server 部署。

    目前，雲端連接器無法與 Lync 或商務用 Skype 內部部署伺服器共存。 如果您想要將現有的 Lync 或商務用 Skype 使用者移 Microsoft 365 並持續提供內部部署的電話語音給使用者，請考慮使用現有商務用 Skype Server 部署的內部部署連線電話系統。 如需詳細資訊，請參閱[plan a 電話系統 (Cloud PBX) 方案](/microsoftteams/cloud-voice-landing-page.md)和[規劃電話系統搭配商務用 Skype Server 中的內部部署 PSTN](plan-phone-system-with-on-premises-pstn-connectivity.md)連線。

- 如果您有先前的商務用 Skype 或 Lync Server 部署，而且您已擴充架構，只要您已移除環境中的所有商務用 Skype 或 lync Server 元件，便不需要清除雲端連接器部署的架構。

- 您的使用者位於線上。

- 如果您的組織已設定目錄同步處理 (DirSync) ，則必須先在內部部署部署中建立規劃混合式語音的所有使用者帳戶，然後再同步到雲端。

- 如有必要，您可以保留目前的 PSTN 載體。

- 如果您想要將電話撥入式會議提供給雲端連接器上所裝載的使用者，您可以購買 PSTN 會議許可證或隨您從 Microsoft 前往音訊會議提供付費。

-  (或隨隨選即付的促銷) 也是通話升級所需的。 如果商務用 Skype 使用者接收來自外部 PSTN 使用者的呼叫，並且想要將另一個參與者新增至該呼叫 (將通話提升至會議) ，則會透過 Microsoft 音訊會議服務執行升級。

- Cloud Connector 2.0 和更新版本現在支援媒體旁路。 媒體旁路可讓用戶端直接將媒體傳送到公用交換電話網路 (PSTN) 下一個躍點（閘道或會話邊界控制器 (SBC) ），並從媒體路徑中消除雲端連接器版本元件。 如需詳細資訊，請參閱 [Plan For 雲端 Connector Edition 中的媒體旁路](plan-for-media-bypass-in-cloud-connector-edition.md)。

- Cloud Connector 2.1 和更新版本支援使用 Operations Management Suite (OMS) 來監視雲端連接器。 如需詳細資訊，請參閱 [使用 Operations Management Suite Monitor Cloud Connector (OMS) ](monitor-cloud-connector-using-operations-management-suite-oms.md)

- 可以使用 Office 365 企業版 E5 的所有國家/地區提供雲端連接器。

本文包含下列章節：

- [雲端連接器版本元件](plan-skype-for-business-cloud-connector-edition.md#BKMK_Components)

- [雲端連接器版本拓撲](plan-skype-for-business-cloud-connector-edition.md#BKMK_Topologies)

- [部署需求](plan-skype-for-business-cloud-connector-edition.md#BKMK_Requirements)

- [部署之前所需收集的資訊](plan-skype-for-business-cloud-connector-edition.md#BKMK_PlanDeployment)

- [撥號對應表考慮](plan-skype-for-business-cloud-connector-edition.md#BKMK_DailPlan)

- [高可用性考慮](plan-skype-for-business-cloud-connector-edition.md#BKMK_HA)

- [雲端連接器媒體流程](plan-skype-for-business-cloud-connector-edition.md#BKMK_MediaFlow)

- [監控及疑難排解](plan-skype-for-business-cloud-connector-edition.md#BKMK_Monitor)

- [相關資訊](plan-skype-for-business-cloud-connector-edition.md#BKMK_MoreInfo)

## <a name="cloud-connector-edition-components"></a>雲端連接器版本元件
<a name="BKMK_Components"> </a>

使用雲端連接器 Edition，您可以部署一組打包的 vm，其中包含最低的商務用 Skype Server 拓撲，包括 Edge 元件、中繼元件，以及中央管理存放區 (CMS) 角色。 您也會安裝網域控制站，此為雲端連接器的內部運作所需的。 這些服務會設定為與您的 Microsoft 365 或包含商務用 Skype 線上服務的 Office 365 組織混合使用。

![雲端連接器版本元件](../../media/f2d4b8a7-c2f4-4cfc-8137-f187399c1298.png)

雲端連接器元件提供下列功能：

- **Edge component** -內部部署拓撲與線上服務之間的通訊會透過 Edge 元件，包括下列元件：

  - **Access Edge** -提供內部部署和商務用 Skype Online 之間的 SIP 路由。

  - **媒體轉送** -提供中繼元件與其他媒體端點之間的媒體路由。

  - **Media 轉送驗證/MRAS** -產生權杖以供存取媒體轉送。

- **輸出路由** -針對連接至雲端連接器裝置的閘道或 SBCs，提供語音流量的負載平衡。 通話會平均分割所有閘道或連接至雲端連接器裝置 SBCs。

    根據原則提供路由傳送至閘道。 只支援以目的地為基礎的全域原則 (輸出) PSTN 號碼。

- **中央管理存放區 (CMS) role** -包括拓撲元件的設定存放區（包括 CMS 檔案傳輸）。

- **中央管理存放區 (cms) 複本** -同步 cms 角色服務器上全域 CMS 資料庫的設定資訊。

- **網域控制站** -Cloud Connector Active Directory 網域服務，用來儲存部署雲端連接器元件所需的所有全域設定和群組。 每個雲端連接器裝置都會建立一個樹系。 網域控制站不能與實際執行 Active Directory 的任何連接。 Active Directory 服務包括：

  - Active Directory Domain Services

  - 發行內部憑證的 Active Directory 憑證服務

- 中繼 **元件**-在商務用 Skype 與 PSTN 閘道之間實現 SIP 和媒體閘道對應通訊協定。 包含一個 CMS 複本，它會同步處理全域 CMS 資料庫的設定。

## <a name="cloud-connector-edition-topologies"></a>雲端連接器版本拓撲
<a name="BKMK_Topologies"> </a>

針對本次討論的目的，我們將會參考 PSTN 網站。 PSTN 網站是雲端連接器裝置的組合，部署于相同位置，並與通用 PSTN 閘道相連。 PSTN 網站可讓您：

- 提供最接近使用者之閘道的連線能力。

- 在一個或多個 PSTN 網站內部署多個雲端連接器裝置，允許可擴充性。

- 在單一 PSTN 網站內部署多個雲端連接器裝置，允許高可用性。

本主題將介紹 PSTN 網站。 如需規劃 PSTN 網站的詳細資訊，請參閱 [Plan For Cloud Connector EDITION PSTN sites](plan-for-cloud-connector-edition-pstn-sites.md)。

您可以部署下列 Cloud Connector 拓撲：

- 每個 PSTN 網站單一雲端連接器 Edition 裝置。 此拓撲僅適用于評估目的，因為它沒有提供高可用性。

- 每個 PSTN 網站多個雲端連接器 Edition 裝置，以提供高可用性。

- 具有多個雲端連接器 Edition 裝置的多個 PSTN 網站，可提供高可用性的可擴充性。 您最多可以部署200網站。

規劃拓撲時，請考慮下列各項：

- 在雲端連接器2.0 和更新版本中，一部 PSTN 網站最多可以有16個雲端連接器裝置。 先前版本支援每個網站最多四個裝置。

- 有兩種類型的硬體設定使用雲端連接器進行測試：

  - 較大的版本可以處理大量同時通話，而且在所有類型的實際生產環境中都支援。

  - 較小的版本是要在低端硬體上執行，而且可用於評估用途，或適用于低通話量的網站。 如果您部署的是較小型的雲端連接器版本，您仍然需要注意生產類別的硬體需求 (例如雙電源供應) 。

- 如果您有雲端連接器版本2.0 或更新版本，且您使用較大的硬體) 部署16裝置 (的最大設定，則您的 PSTN 網站可以處理最多8000同時通話。 如果您部署的是較小的版本，支援的限制為800。

    您也需要專用某些裝置以取得高可用性。 最小建議是一個裝置應該保留以取得高可用性。

  - 使用第2版時，如果您部署了 15 + 1 設定，您的 PSTN 網站可以處理最多7500同時通話。

  - 如果您有較舊的版本，且使用較大的硬體) 部署最多 3 + 1 設定 (，則您的 PSTN 網站最多可以處理1500同時通話。 如果您部署的是較小的版本，支援的限制為150。

-  如果您需要每個 PSTN 網站有多個通話，您可以在相同位置部署其他 PSTN 網站，以進行擴充。

> [!NOTE]
> 除非另有說明，否則以下的圖表和範例會假設使用的是較大版本的雲端連接器。

### <a name="single-cloud-connector-appliance-within-a-single-pstn-site"></a>單一 PSTN 網站內的單一雲端連接器裝置

下圖顯示單一 PSTN 網站內的單一雲端連接器 Edition 裝置。 請注意，雲端連接器是由四個 Vm 組成，這些 Vm 是安裝在周邊網路中的一部實體主機上，以進行安全性用途。

![具有一個 PSTN 網站的一個雲端連接器](../../media/7ffe6953-8c66-4323-940e-cd2e6c3c2a66.png)

### <a name="multiple-cloud-connector-appliances-within-a-single-pstn-site"></a>單一 PSTN 網站中的多個雲端連接器裝置

 出於可伸縮性和高可用性的目的，您可以選擇在單一 PSTN 網站內有多個雲端連接器版本，如下圖所示。 考慮下列事項：

- 通話會以隨機順序分配至一個集區中的雲端連接器。

- 針對容量規劃的目的，您必須考慮在一或多個雲端連接器離線時處理負載的能力，其依據如下的計算：

  - **N + 1 方塊。** 針對較大型版本的雲端連接器，N + 1 方塊支援 500 \* N 並行通話，具有99.8% 的可用性。

    若為較小型版本的雲端連接器，N + 1 方塊支援 50 \* N 同時通話，具有99.8% 的可用性。

  - **N + 2 方塊。** 針對較大型版本的雲端連接器，N + 2 方塊支援 500 \* N 同時通話，具有99.9% 的可用性。

    若為較小型版本的雲端連接器，N + 2 方塊支援 50 \* N 同時通話，具有99.9% 的可用性。

![1 PSTN 網站中的兩個雲端連接器](../../media/fc0dc47f-5595-42cb-9432-9c8ff3e134e9.png)

### <a name="multiple-pstn-sites-with-one-or-more-cloud-connectors-per-site"></a>每個網站有一個或多個雲端連接器的多個 PSTN 網站

您也可以選擇在每個網站中有多個具有一個或多個雲端連接器版本的 PSTN 網站。 如果您的 PSTN 網站達到同時呼叫的限制，您可以新增另一個 PSTN 網站來處理負載。

多個 PSTN 網站也可讓您提供最接近使用者之閘道的連線能力。 例如，假設您在西雅圖和阿姆斯特丹中有 PSTN 閘道。 您可以部署兩部 PSTN 網站（一個在西雅圖，一個在阿姆斯特丹中），並指派使用者使用最接近的 pstn 網站。 西雅圖的使用者將會路由傳送到西雅圖 PSTN 網站和閘道，而將阿姆斯特丹中的使用者路由傳送至阿姆斯特丹 PSTN 網站和閘道：

![兩個 PSTN 網站內的雲端連接器版本](../../media/16ead6d3-67da-4e71-b4d5-d895b4c9384e.png)

## <a name="requirements-for-deployment"></a>部署需求
<a name="BKMK_Requirements"> </a>

部署雲端連接器 Edition 之前，請確定您的環境具備下列各項：

- **針對主機機-** 雲端連接器 vm 必須部署在已啟用 Hyper-V role (英文) 的專用硬體上，以執行 Windows Server 2012 R2 Datacenter edition。

    針對版本2.0 和更新版本，系結至商務用 Skype 網路網路的交換器的主機電腦網路卡，必須在與雲端連接器公司網路機器相同的子網中設定 IP 位址。

- 針對2.1 和更新版本，主機裝置必須已安裝 .NET Framework 4.6.1 或更新版本。

- **針對虛擬機器-** Windows Server 2012 R2 ISO (英文) 映射 ( ISO) 。 ISO 將會轉換成 vhd，以供將執行商務用 Skype Cloud Connector Edition 的虛擬機器。

- 在您的部署中支援每個雲端連接器 Edition 安裝4個 Vm 所需的硬體。 建議使用下列設定：

  - 64位雙處理器，六個核心 (12 個實核心) ，2.50 十億位元 (GHz) 或更高版本

  - 64 gb (GB) ECC RAM

  - 4 600 GB (或更好) 10K RPM 128M 快取 SAS 6 Gbps 磁片，已在 RAID 5 設定中設定

  - 3 1 Gbps RJ45 高輸送量網路介面卡

- 如果您選擇部署支援高達50同時通話的較小版本的雲端連接器版本，則需要下列硬體：

  - Intel i7 4790 四核含英特爾4600圖形 (無需高端圖形) 

  - 32 GB DDR3-1600 非 ECC

  - 2: 1 TB 7200RPM SATA III (6 Gbps) 在 RAID 0

  - 2: 1 Gbps 乙太 (RJ45) 

- 若主機電腦需要有 proxy 伺服器來流覽網際網路，則您必須進行下列設定變更：

  - 若要略過 proxy，請指定使用 proxy 伺服器設定 WinHTTP Proxy 設定，以及包含 " \* 192.168.213" 的旁路清單。您的雲端連接器 Managements 服務和商務用 Skype 網路服務子網所用的網路，如您 CloudConnector.ini 檔案中所定義。 否則，管理連線會失敗並避免雲端連接器的部署和自動修復。 以下是一個範例 winHTTP 設定命令： netsh winHTTP set proxy "10.10.10.175： 8080" 旁路-list = " \* local; 1. \* ;172.20. \* ; 192.168.218. \* ' \<local\> "。

  - 指定每個機器的 proxy 設定，而非每個使用者。 否則 Cloud Connector 下載將會失敗。 您可以使用登錄變更或「群組原則」設定來指定每台電腦的 proxy 設定，如下所示：

  - **Registry：** HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows\CurrentVersion\Internet Settings] ProxySettingsPerUser dword：00000000

  - **群組原則：** 電腦系統 \> 管理範本 \> Windows 元件 \> Internet Explorer：針對每個機器 (設定 Proxy 設定，而不是依據每個使用者進行) 

- 合格的 PBX/主幹或合格的 SBC/閘道 () 建議至少兩個閘道。

    雲端連接器支援相同的會話邊界控制器 (已驗證商務用 Skype 的 SBCs) 。 如需詳細資訊，請參閱用於[商務用 Skype 的電話語音基礎結構](../../../SfbPartnerCertification/certification/infra-gateways.md)。

- 本機伺服器管理員帳戶，具有在主伺服器上安裝及設定 Hyper-V 的許可權。 此帳戶必須在安裝及設定 Hyper-V 的本機伺服器上具有系統管理員許可權。

- 在部署期間，系統會要求您建立具有許可權的網域管理員帳戶，以在雲端連接器網域中建立及發行拓撲。

- 在安裝套件隨附的 CloudConnector.ini 檔案中定義的外部 DNS 記錄：

  - Edge 元件的 Access Edge service 的外部 DNS 記錄;例如， \<Domain Name\> ap。 您需要每個 PSTN 網站有一筆記錄。 此記錄必須包含該網站所有邊緣的 IP 位址。

- 會建立所有必要的 DNS 和 SRV 記錄的 Microsoft 365 或 Office 365 組織。

    > [!IMPORTANT]
    > 當您將租使用者與 Cloud Connector Edition 整合時，不支援使用預設網域尾碼 onmicrosoft.com，做為組織的 SIP 網域。 > 您無法使用 sip。\<Domain Name\> 做為您的雲端連接器 Edge Access proxy 介面的名稱，因為 Microsoft 365 和 Office 365 使用此 DNS 記錄。

- 從公用憑證授權單位取得之外部 Edge 的憑證 (CA) 。

- 允許流量已完成之必要端口的防火牆規則。

- 主機和虛擬機器的網際網路連線。 雲端連接器會從網際網路下載部分軟體;因此，您必須提供閘道和 DNS 伺服器資訊，使雲端連接器主機電腦與 Vm 可以連線到網際網路，並下載必要的軟體。

- 安裝在主機電腦上的承租人遠端 PowerShell 模組。

- 商務用 Skype 的系統管理員認證，以執行遠端 PowerShell。

    > [!IMPORTANT]
    > 管理員帳戶不得啟用多重要素驗證。

> [!NOTE]
> 僅 Microsoft Hyper-V 虛擬化平臺上支援雲端連接器部署。 不支援其他平臺（如 VMware 和 Amazon Web 服務）。

> [!NOTE]
> 執行雲端連接器的最低硬體指引是以基本硬體容量為基礎的 (核心、MHz、gb 等等) ，但有一些緩衝區可容納因在任何電腦架構中的無形效能障礙。 Microsoft 已于商業用的硬體會議上執行最壞的案例負載測試，這是最低的指導方針。 已驗證媒體質量和系統效能。 官方 Cloud Connector 裝置合作夥伴的 Microsoft 有特定的雲端連接器硬體實施，其具有獨立測試的效能，而且其硬體適用性可滿足負載和品質需求。

> [!NOTE]
> AudioCodes 和 Sonus 所產生的裝置，已修改程式碼，並在 Windows Server Standard edition 的伺服器上執行。 支援這些裝置。

## <a name="information-you-need-to-gather-before-deployment"></a>部署之前所需收集的資訊
<a name="BKMK_PlanDeployment"> </a>

開始部署之前，您必須決定部署的大小、所服務的 SIP 網域，以及您規劃要部署之每個 PSTN 網站的設定資訊。 若要開始，您可以：

- 根據您公司所使用的 SIP URIs，識別將由此部署提供服務的所有 SIP 網域。

- 決定您需要部署的 PSTN 網站數目。

- 確定您有必要的硬體，以支援您將為每個雲端連接器版本安裝的四個 Vm。

針對您計畫要部署的每個 PSTN 網站，您必須：

- 為每個雲端連接器裝置中的所有元件建立名稱 (請參閱 [判斷 deployment parameters](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams)) 。

- 定義埠範圍 (請參閱) 的 [埠和通訊協定](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports) 。

- 建立 Edge 元件的外部 DNS 記錄 (請參閱 [部署](plan-skype-for-business-cloud-connector-edition.md#BKMK_Requirements)) 的需求。

- 決定 Edge 元件的憑證需求 (請參閱) 的 [憑證需求](plan-skype-for-business-cloud-connector-edition.md#BKMK_Certs) 。

### <a name="ports-and-protocols"></a>連接埠和通訊協定
<a name="BKMB_Ports"> </a>

定義媒體埠範圍時，請注意下列事項：

- 用戶端永遠使用埠範圍50000至50019進行媒體流量-此範圍已在線上商務用 Skype 中預先定義，而且無法變更。

- 根據預設，中繼元件會使用埠範圍 49 152 至 57 500 進行媒體流量。 不過，連線是透過內部防火牆建立的，而且由於安全性原因，您可以限制拓撲中的此埠範圍。 每次通話時，最多隻需要四個埠。 如果您想要限制中繼元件與 PSTN 閘道之間的埠數目，您也需要在閘道上設定對應的埠範圍。

- 您必須在周邊網路中部署雲端連接器。 這表示您會有兩個防火牆：

  - 第一個防火牆是網際網路與周邊網路之間的外部防火牆。

  - 第二個防火牆是周邊網路和您的內部網路之間的內部。

    您的用戶端可以位於網際網路或內部網路中：

  - 網際網路中的用戶端會透過 Edge 元件透過外部防火牆連接至您的 PSTN。

  - 內部網路中的用戶端會透過內部防火牆連接至周邊網路中的中繼元件，這會將流量連接至 SBC 或 PSTN 閘道。

    這表示您必須在這兩個防火牆中開啟埠。

下表說明外部和內部防火牆的埠及埠範圍。

此表格顯示埠及埠範圍，以啟用內部網路和中繼元件中用戶端之間的通訊：

**內部防火牆**



|**來源 IP**|**目的地 IP**|**來源連接埠**|**目的地連接埠**|
|:-----|:-----|:-----|:-----|
|雲端連接器轉送元件  <br/> |SBC/PSTN 閘道  <br/> |任何  <br/> |TCP 5060\*\*  <br/> |
|SBC/PSTN 閘道  <br/> |雲端連接器轉送元件  <br/> |任何  <br/> |TCP 5068/TLS 5067  <br/> |
|雲端連接器轉送元件  <br/> |SBC/PSTN 閘道  <br/> |UDP 49 152-57 500  <br/> |任何\*\*\*  <br/> |
|SBC/PSTN 閘道  <br/> |雲端連接器轉送元件  <br/> |任何\*\*\*  <br/> |UDP 49 152-57 500  <br/> |
|雲端連接器轉送元件  <br/> |內部用戶端  <br/> |TCP 49 152-57 500\*  <br/> |TCP 50000 50019  <br/> (選用)  <br/> |
|雲端連接器轉送元件  <br/> |內部用戶端  <br/> |UDP 49 152-57 500\*  <br/> |UDP 50000 50019  <br/> |
|內部用戶端  <br/> |雲端連接器轉送元件  <br/> |TCP 50000 50019  <br/> |TCP 49 152-57 500\*  <br/> |
|內部用戶端  <br/> |雲端連接器轉送元件  <br/> |UDP 50000 50019  <br/> |UDP 49 152-57 500\*  <br/> |

\* 這是中繼元件上的預設埠範圍。 為了達到最佳的通話流程，需要每個通話有四個埠。

\*\* 此埠必須設定在 SBC/PSTN 閘道上;5060為範例。 您可以在 SBC/PSTN 閘道上設定其他埠。

\*\*\* 請注意，如果 SBC/閘道製造商允許，您也可以限制 SBC/閘道上的埠範圍。

基於安全性的考慮，您可以使用 [Set-CsMediationServer](/powershell/module/skype/set-csmediationserver?) Cmdlet 來限制中繼元件的埠範圍。

例如，下列命令會限制在) 中，中繼元件將用於音訊 (的媒體流量為 50 000-51 000 的埠數目。 中繼元件將可以使用此設定來處理250同時進行的呼叫。 請注意，您也可能想要在 SBC/PSTN 閘道上限制此範圍：

```powershell
Set-CSMediationServer -Identity MediationServer:mspool.contoso.com -AudioPortStart 50000 - AudioPortCount 1000
```

若要取得轉送元件的名稱並查看預設埠，您可以使用 [Get-CsService](/powershell/module/skype/get-csservice?) Cmdlet，如下所示：

```powershell
Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount
```

下表顯示啟用雲端連接器 Edge 元件與外部防火牆之間通訊的埠及埠範圍。 下表顯示最低建議。

在此情況下，網際網路的所有流量都會透過線上邊緣流過，如下所示：使用者端-- \> 線上 edge-- \> Cloud Connector Edge：

**外部防火牆-最低設定**



|**來源 IP**|**目的地 IP**|**來源埠**|**目的地埠**|
|:-----|:-----|:-----|:-----|
|任何  <br/> |Cloud Connector Edge 外部介面  <br/> |任何  <br/> |) 5061 的 TCP (MTLS  <br/> |
|Cloud Connector Edge 外部介面  <br/> |任何  <br/> |任何  <br/> |) 5061 的 TCP (MTLS  <br/> |
|Cloud Connector Edge 外部介面  <br/> |任何  <br/> |任何  <br/> |TCP 80  <br/> |
|Cloud Connector Edge 外部介面  <br/> |任何  <br/> |任何  <br/> |UDP 53  <br/> |
|Cloud Connector Edge 外部介面  <br/> |任何  <br/> |任何  <br/> |TCP 53  <br/> |
|Cloud Connector Edge 外部介面  <br/> |任何  <br/> |UDP 3478  <br/> |UDP 3478  <br/> |
|任何  <br/> |Cloud Connector Edge 外部介面  <br/> |TCP 50000 59999  <br/> |TCP 443  <br/> |
|任何  <br/> |Cloud Connector Edge 外部介面  <br/> |UDP 3478  <br/> |UDP 3478  <br/> |
|Cloud Connector Edge 外部介面  <br/> |任何  <br/> |TCP 50000 59999  <br/> |TCP 443  <br/> |

下表顯示埠及埠範圍，以啟用雲端連接器 Edge 元件與外部防火牆之間的通訊。 下表顯示建議的解決方案。

在此情況下，網際網路中終點的所有媒體流量都可以直接流向雲端連接器 Edge 元件。 媒體路徑會是使用者端點- \> Cloud Connector Edge。

> [!NOTE]
> 如果使用者結束點位於對稱 NAT 之後，此解決方案將無法運作。

**外部防火牆-建議設定**


|**來源 IP**|**目的地 IP**|**來源連接埠**|**目的地連接埠**|
|:-----|:-----|:-----|:-----|
|任何  <br/> |Cloud Connector Edge 外部介面  <br/> |任何  <br/> |) 5061 的 TCP (MTLS  <br/> |
|Cloud Connector Edge 外部介面  <br/> |任何  <br/> |任何  <br/> |) 5061 的 TCP (MTLS  <br/> |
|Cloud Connector Edge 外部介面  <br/> |任何  <br/> |任何  <br/> |TCP 80  <br/> |
|Cloud Connector Edge 外部介面  <br/> |任何  <br/> |任何  <br/> |UDP 53  <br/> |
|Cloud Connector Edge 外部介面  <br/> |任何  <br/> |任何  <br/> |TCP 53  <br/> |
|Cloud Connector Edge 外部介面  <br/> |任何  <br/> |TCP 50000 59999  <br/> |任何  <br/> |
|Cloud Connector Edge 外部介面  <br/> |任何  <br/> |UDP 3478;UDP 50000 59999  <br/> |任何  <br/> |
|任何  <br/> |Cloud Connector Edge 外部介面  <br/> |任何  <br/> |TCP 443;TCP 50000 59999  <br/> |
|任何  <br/> |Cloud Connector Edge 外部介面  <br/> |任何  <br/> |UDP 3478;UDP 50000-59999  <br/> |

### <a name="host-internet-connectivity-requirements"></a>主機網際網路連線性需求
<a name="BKMB_Ports"> </a>

主機機器必須能夠接觸外部資源，才能成功安裝、更新及管理雲端連接器。 下表顯示主機電腦與外部資源之間所需的目的地及埠。

|方向  <br/> |來源 IP  <br/> |目的地 IP  <br/> |來源連接埠  <br/> |目的地連接埠  <br/> |Protocol (通訊協定)  <br/> |用途  <br/> |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|出埠  <br/> |雲端連接器主機 IPs  <br/> |任何  <br/> |任何  <br/> |53  <br/> |TCP/UDP  <br/> |DNS  <br/> |
|出埠  <br/> |雲端連接器主機 IPs  <br/> |任何  <br/> |任何  <br/> |80，443  <br/> |TCP  <br/> | (CRL) 的憑證吊銷清單  <br/> |
|出埠  <br/> |雲端連接器主機 IPs  <br/> |任何  <br/> |任何  <br/> |80，443  <br/> |TCP  <br/> |雲端連接器更新  <br/> 商務用 Skype Online  <br/> 系統管理員 PowerShell  <br/> Windows Update  <br/> |

如果需要更嚴格的規則，請參閱下列 allowlist URLs：

- [Office 365 URLs 和 IP 位址範圍](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)中[URLs 的憑證吊銷清單](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)

- Windows更新：[如何設定軟體更新的防火牆](https://technet.microsoft.com/library/bb693717.aspx)

- 商務用 Skype線上系統管理員 PowerShell: \* 。 online.lync.com

    如果您需要此目的地的 proxy 排除，您必須將其新增至 WinHTTP 旁路清單。

- 雲端連接器更新： [下載中心](https://aka.ms/CloudConnectorInstaller)、 [https://go.microsoft.com](https://go.microsoft.com) 和 [https://download.microsoft.com](https://download.microsoft.com)

### <a name="dns-name-resolution-for-the-edge-component"></a>Edge 元件的 DNS 名稱解析
<a name="BKMB_Ports"> </a>

Edge 元件必須解析 Microsoft 365 或 Office 365 服務的外部名稱，以及其他雲端連接器元件的內部名稱。

每個 Edge 元件都是具有外部及內部介面的多穴電腦。 雲端連接器會在周邊網路中的網域控制站元件上部署 DNS 伺服器。 您可以將 Edge Server 指向周邊中的 DNS 伺服器，以用於所有名稱解析，但是您必須啟用雲端連接器 DNS 伺服器來解析外部名稱，方法是設定 DNS 區域，其中包含一個或多個引用名稱查閱至其他公用 DNS 伺服器的外部查詢的 DNS A 記錄。

在 .ini 檔案中，如果您將閘道的 FQDN 名稱設為與 SIP 網域相同的網域空間，則會在周邊伺服器的 DNS 伺服器中建立此 SIP 網域的授權區域。 如果 Edge Server 指向此 DNS 伺服器以解析名稱，則 Edge 永遠不會解析 _sipfederationtls。\<yourdomain\> DNS 記錄，這是通話流程的必要條件。 在此情況下，Microsoft 建議您在 Edge 外部介面上提供 DNS 伺服器，以解析網際網路名稱查閱，而且每個 Edge 元件都必須使用主機檔來解析其他 Cloud Connector 元件名稱至 IP 位址。

> [!NOTE]
> 基於安全性考慮，建議您不要將雲端連接器 DNS 伺服器指向實際執行網域中的內部伺服器，以進行名稱解析。

### <a name="determine-deployment-parameters"></a>決定部署參數
<a name="BKMK_SiteParams"> </a>

首先，您必須定義下列常見的部署參數：


|**項目**|**描述**|**附註**|
|:-----|:-----|:-----|
|SIP 網域  <br/> |公司使用者使用的 SIP URI。 提供此部署將服務的所有 SIP 網域。 您可以擁有一個以上的 SIP 網域。  <br/> ||
|PSTN 網站數目  <br/> |您將部署的 PSTN 網站數目。  <br/> ||

針對您計畫要部署的每個 PSTN 網站，您必須先收集下列資訊，然後再開始部署。 當您更新 CloudConnector.ini 檔時，您將需要提供此資訊。

設定閘道資訊時，請記住下列事項：

- 如果您只有一個閘道，請在第二個閘道的 .ini 檔案中移除區段。 若有兩個以上的閘道，請遵循現有的格式來新增新的。

- 請確定閘道 (s) 的 IP 位址與埠是否正確。

- 若要支援 PSTN 閘道層級 HA，請保留輔助閘道或新增其他閘道。

 (選用) 若要限制撥出電話號碼，請更新 LocalRoute 值。



|**網站參數**|**描述**|**附註**|
|:-----|:-----|:-----|
|虛擬機器功能變數名稱  <br/> |雲端連接器內部元件的功能變數名稱。 此網域必須不同于實際執行網域。 名稱在所有雲端連接器裝置上必須相同。  <br/> .ini 檔案名中的名稱： "VirtualMachineDomain"  <br/> |。本地域是可取的。  <br/> |
|雲端連接器網域控制站名稱  <br/> |網域控制站的名稱。  <br/> .ini 檔案名中的名稱： "ServerName"  <br/> |不得超過15個字元。 請僅輸入 Netbios 名稱。  <br/> |
|雲端連接器網域控制站 IP/子網路遮罩  <br/> |網域控制站的 IP 位址。  <br/> .ini 檔案名中的名稱： "IP"  <br/> ||
|Microsoft 365 或 Office 365 線上服務 fqdn  <br/> |在大部分情況下，全域 Microsoft 365 或 Office 365 實例的預設值都必須是預設值。  <br/> .ini 檔案名中的名稱： "OnlineSipFederationFqdn"  <br/> ||
|SiteName  <br/> |商務用 Skype 網站名稱;例如，西雅圖。  <br/> .ini 檔案名中的名稱： "SiteName"  <br/> 針對發行1.4.1 及更新版本，每個網站的網站名稱必須不同，且名稱必須符合 PSTN 網站（如果存在），且已在 Microsoft 365 或 Office 365 中定義。 請注意，註冊網站中的第一個裝置時，系統會自動建立 PSTN 網站。  <br/> ||
|HardwareType  <br/> 發行1.4.1 及更新版本  <br/> |硬體類型。 預設值為 Normal。 您也可以設定為 [最小值]。  <br/> ||
|國碼  <br/> |用於撥號的國家/地區號碼。  <br/> .ini 檔案名中的名稱： "CountryCode"  <br/> ||
|鄉/鎮/市/區  <br/> |城市 (選用) 。  <br/> .ini 檔案名中的名稱： "City"  <br/> ||
|狀態  <br/> |狀態 (選用) 。  <br/> .ini 檔案名中的名稱： "State"  <br/> ||
|基底 VM IP 位址  <br/> |將用來建立所有雲端連接器虛擬機器之 VHDX 的臨時基底 VM 的 IP 位址。 這個 IP 必須在下一個步驟中定義的周邊公司網路子網中，且需要網際網路存取權。 請務必定義公司的預設閘道和可路由傳送至網際網路的 DNS。  <br/> .ini 檔案名中的名稱： "BaseVMIP"  <br/> ||
|WSUSServer  <br/> WSUSStatusServer  <br/> 發行1.4.1 及更新版本  <br/> |Windows Server Update Services (WSUS) （內部網路伺服器）以從 Microsoft Update 中主控更新的位址。  <br/> 如果不需要 WSUS，您可以保留空白。  <br/> ||
|內部網路的子網路遮罩  <br/> |雲端連接器會設定 IP 網路，以用於雲端連接器元件之間的內部通訊。 Edge 也必須連接到另一個允許網際網路連線的子網。  <br/> .ini 檔案中的名稱： "CorpnetIPPrefixLength" 底下的「VM 網路集區的集區」  <br/> ||
|外部網路的子網路遮罩  <br/> |針對 Edge 元件的外部網路。  <br/> .ini 檔案中的名稱： "InternetIPPrefix" 底下的「VM 網路集區的集區」  <br/> ||
|內部網路的切換名稱  <br/> |將用於內部雲端連接器網路的參數名稱。  <br/> 在大多數情況下，您可以使用預設的建議值。  <br/> .ini 檔案中的名稱： "CorpnetSwitchName" 底下的 VM 網路集區的 [參數]  <br/> ||
|外部網路的切換名稱  <br/> |將用於外部雲端連接器網路的參數名稱。  <br/> 在大多數情況下，您可以使用預設的建議值。  <br/> .ini 檔案中的名稱： "InternetSwitchName" 底下的 VM 網路集區的 [參數]  <br/> ||
|內部網路的預設閘道  <br/> |此閘道必須提供對網際網路的存取。 (網際網路也需要設定 DNS 伺服器) ，且會設定在雲端連接器元件的內部介面上。  <br/> .ini 檔案中的名稱： "CorpnetDefaultGateway" 底下的 VM 網路集區的 [參數]  <br/> ||
|Edge 元件外部介面的預設閘道  <br/> |會在 Edge 元件的外部介面上進行設定。  <br/> .ini 檔案中的名稱： "InternetDefaultGateway" 底下的 VM 網路集區的 [參數]  <br/> ||
|內部網路的 DNS 伺服器  <br/> |會在臨時 VM 的內部介面上進行設定。 必須為網際網路名稱提供名稱解析。 若未提供 DNS 伺服器，網際網路連線將會失敗，而且不會完成部署。  <br/> .ini 檔案中的名稱： "CorpnetDNSIPAddress" 底下的 VM 網路集區的 [參數]  <br/> ||
|Edge 元件外部介面的 DNS 伺服器  <br/> |會在 Edge 的外部介面上進行設定。  <br/> .ini 檔案中的名稱： "InternetDNSIPAddress" 底下的 VM 網路集區的 [參數]  <br/> ||
|管理參數名稱  <br/> |管理參數是一種暫存參數，會自動建立，並在部署期間用於雲端連接器的設定。 部署之後，它會自動中斷連線。 它必須與雲端連接器中所用的任何其他網路具有不同的子網。  <br/> 在大多數情況下，您可以使用預設的建議值。  <br/> .ini 檔案中的名稱： "ManagementSwitchName" 底下的 VM 網路集區的 [參數]  <br/> ||
|管理子網位址/子網路遮罩  <br/> |管理子網是會自動建立的臨時子網，在部署期間將用來設定雲端連接器。 部署後會自動移除它。 它必須與雲端連接器中所用的任何其他網路具有不同的子網。  <br/> 在 .ini 檔案中的名稱： "ManagementIPPrefix" 和 "ManagementIPPrefixLength" 下的「VM 網路集區」的參數  <br/> ||
|中央管理存放區 (CMS) 機器  <br/> |用於中央管理存放區 (CMS) 的單一 FQDN。 AD 功能變數名稱將用來產生 FQDN。  <br/> .ini 檔案中的名稱： "ServerName" （位於 "Primary Central Management Service 的參數）" 底下  <br/> |不得超過15個字元。 請僅輸入 Netbios 名稱。  <br/>  (CMS 集區名稱 = 伺服器名稱)   <br/> |
|CMS 電腦 IP 位址  <br/> | (周邊網路) 內部的 CMS 伺服器的 IP 位址。  <br/> INI 檔案中的名稱：「IP」，主要管理中心服務的參數  <br/> ||
|檔案共用名稱稱  <br/> |要在 CMS 伺服器上為商務用 Skype 複寫資料 (建立的檔案共用名稱稱，例如，CmsFileStore) 。  <br/> 在大多數情況下，您可以使用預設的建議值。  <br/> .ini 檔中的名稱： "CmsFileStore" 在 [主要管理中心服務的參數] 底下  <br/> ||
|中繼元件集區名稱  <br/> |中繼元件的集區名稱。 請僅輸入 Netbios 名稱。 AD 功能變數名稱將用來產生 FQDN。  <br/> .ini 檔的名稱： "PoolName" 底下的「轉送伺服器集區的參數」  <br/> |不得超過15個字元。 請僅輸入 Netbios 名稱。  <br/> |
|轉送元件名稱  <br/> |中繼元件1的元件名稱。 請僅輸入 Netbios 名稱。 AD 功能變數名稱將用來產生 FQDN。  <br/> .ini 檔案中的名稱： "ServerName" 下的「轉送伺服器集區」的 [參數]  <br/> |不得超過15個字元。 請僅輸入 Netbios 名稱。  <br/> |
|中繼元件電腦 IP 位址  <br/> |在周邊網路) 中內部的中繼元件 (內部網路的 IP。  <br/> .ini 檔中的名稱： "IP"，位於 "轉送伺服器集區的參數] 底下。  <br/> ||
|Edge 集區內部名稱  <br/> |Edge 元件的集區名稱。 請僅輸入 Netbios 名稱。 AD 功能變數名稱將用來產生 FQDN。  <br/> .ini 檔中的名稱： "InternalPoolName" 底下的 [Edge Servers 集區的參數]  <br/> |不得超過15個字元。 請僅輸入 Netbios 名稱。  <br/> |
|Edge Server 內部名稱  <br/> |Edge 元件的元件名稱。 請僅輸入 Netbios 名稱。 AD 功能變數名稱將用來產生 FQDN。  <br/> .ini 檔中的名稱： "InternalServerName" 底下的 [Edge Servers 集區的參數]  <br/> |不得超過15個字元。 請僅輸入 Netbios 名稱。  <br/> |
|Edge server 內部 IP  <br/> |Edge 元件的內部周邊網路 IP，以與 Cloud Connector 的其他元件通訊。  <br/> .ini 檔中的名稱： "InternalServerIPs" 底下的 [Edge Servers 集區的參數]  <br/> ||
|存取集區外部名稱  <br/> |Access Edge 的名稱;例如，AP。 此名稱必須符合為 SSL 憑證所提供的名稱。 請僅輸入 Netbios 名稱。 SIP 功能變數名稱將用來產生 FQDN。 一個外部集區名稱將用於集區中的所有 Edge 元件。 每個 PSTN 網站需要一個 Edge Access 集區。  <br/> .ini 檔中的名稱： "ExternalSIPPoolName" 底下的 [Edge Servers 集區的參數]  <br/> |不得超過15個字元。 請僅輸入 Netbios 名稱。  <br/> "sip" 是保留的，因此無法用作名稱。  <br/> 產生的 FQDN 名稱必須符合為 SSL 憑證所提供的名稱。  <br/> |
|Access Edge 的外部 IP  <br/> |Edge 元件的外部 IP （如果沒有 NAT 可供使用，或已轉譯的 IP (指定對應) 的兩個位址。  <br/> .ini 檔中的名稱： "ExternalSIPIPs" 底下的 [Edge Servers 集區的參數]  <br/> ||
|媒體轉送名稱  <br/> |音訊影片媒體轉送 Edge 的名稱;例如先生。 一個外部集區名稱將用於集區中的所有 Edge 元件。 每個 PSTN 網站需要一個 Edge Media 轉送集區。  <br/> .ini 檔中的名稱： "ExternalMRFQDNPoolName" 底下的 [Edge Servers 集區的參數]  <br/> |不得超過15個字元。 請僅輸入 Netbios 名稱。  <br/> |
|媒體轉送 Edge 的外部 IP  <br/> |目前只支援一個 IP，因此這會與 Access Edge 相同（公用或對應的 IP (）在對應) 時指定這兩個位址。 可以是 Access Edge 之 Edge 元件的外部 IP 位址。 附注如果 Edge 位於 NAT 背後，您也必須指定下一個參數的值。  <br/> .ini 檔中的名稱： "ExternalMRIPs" 底下的 [Edge Servers 集區的參數]  <br/> ||
|Media 轉送 Edge 的外部 IP (如果 Edge 位於 NAT 之後)   <br/> |如果您的 Edge 位於 NAT 之後，您也必須指定 NAT 裝置的公用位址。  <br/> .ini 檔中的名稱： "ExternalMRPublicIPs" 底下的 [Edge Servers 集區的參數]  <br/> ||
|語音閘道1制定和模型  <br/> |指定 SBC/Voice 閘道的 make 和 model。 請注意，您可以從已測試裝置清單中連接裝置或 SIP 主幹 [https://technet.Microsoft.com/UCOIP](../../../SfbPartnerCertification/certification/overview.md) 。  <br/> ||
|如果您有兩個以上的閘道，則為語音閘道 2 Make and Model (複製此列)   <br/> |指定語音閘道的制定和模型。 請注意，您可以從已測試裝置清單中連接裝置 [https://technet.Microsoft.com/UCOIP](../../../SfbPartnerCertification/certification/overview.md) 。  <br/> ||
|語音閘道1名稱  <br/> |用於產生電腦 FQDN 與 AD 網域。 若要在中繼元件和語音閘道之間使用 TLS，則為必要的。 如果您不打算使用 FQDN，例如，TLS 不是必要的，或語音閘道不支援使用 FQDN (唯一的 IP) —指定。  <br/> ||
|語音閘道2名稱 (複製此列（如果您有超過2個閘道)   <br/> |用於產生電腦 FQDN 與 AD 網域。 若 TLS 將用於中繼元件和語音閘道，則為必要。 如果您不打算使用 FQDN，例如，TLS 不是必要的，或語音閘道不支援使用 FQDN (唯一的 IP) —指定。  <br/> ||
|語音閘道 1 IP 位址  <br/> |語音閘道的 IP 位址。  <br/> ||
|語音閘道 2 IP 位址 (複製此列（如果您有兩個以上的閘道）)   <br/> |語音閘道的 IP 位址。  <br/> ||
|語音閘道1埠 # (複製此列（如果您有兩個以上的閘道）)   <br/> |語音閘道 SIP 主幹會接聽的埠，例如5060。  <br/> ||
|語音閘道2埠#  <br/> |語音閘道 SIP 主幹會接聽的埠，例如5060。  <br/> ||
|適用于 SIP 流量的語音閘道1通訊協定  <br/> |TCP 或 TLS。  <br/> ||
|適用于 SIP 流量的語音閘道2通訊協定 (複製此列（如果您有超過2個閘道）)   <br/> |TCP 或 TLS。  <br/> ||
|進出 Edge 元件之流量的外部媒體埠範圍  <br/> |TCP/UDP edge 的外部介面的媒體流量的埠範圍。 必須永遠從 50 000 開始。 如需詳細資訊，請參閱「埠和通訊協定」。  <br/> |50000-59 999  <br/> |
|透過內部防火牆與中繼元件進行通訊的媒體埠範圍  <br/> |中繼元件要用來與用戶端和閘道通訊的 UDP 埠範圍 (每次呼叫的建議4個埠) 。  <br/> ||
|從商務用 Skype 用戶端透過內部防火牆進行通訊的媒體埠範圍  <br/> |出於規劃目的，無法變更。 需要在內部防火牆中開啟埠，以在內部網路和中繼元件的商務用 Skype 用戶端之間進行通訊。  <br/> |50 000-50 019  <br/> |
|公用憑證密碼  <br/> |必須在腳本中提供。  <br/> ||
|保管庫模式系統管理員密碼  <br/> 僅限版本1.4。2  <br/> |內部 CC 網域的保管庫模式系統管理員密碼。  <br/> ||
|雲端連接器網域管理員密碼  <br/> 僅限版本1.4。2  <br/> |雲端連接器網域管理員的密碼 (不同于您的實際執行網域) 。 使用者名稱為系統管理員。 您無法變更使用者名稱。  <br/> ||
|虛擬機器管理員密碼  <br/> 僅限版本1.4。2  <br/> |在部署期間用來設定管理網路。  <br/> 使用者名稱為系統管理員。 您無法變更使用者名稱。  <br/> ||
|CABackupFile  <br/> 版本2.0 和更新版本  <br/> |用於在雲端連接器網站中部署多個裝置時，將憑證授權單位服務從 Active Directory 伺服器儲存至檔案。 請務必為一個雲端連接器網站中的所有裝置使用相同的密碼，以便將 CA 備份檔案匯入至已成功新增的裝置。  <br/> ||
|CCEService  <br/> 版本2.0 和更新版本  <br/> |用於雲端連接器管理服務;需要存取雲端連接器網站目錄。 請務必為一個雲端連接器網站內的所有裝置使用相同的密碼。  <br/> ||
|Microsoft 365 或 Office 365 租使用者管理員  <br/> | 雲端連接器會使用此帳戶來更新及管理雲端連接器的租使用者設定： <br/>  版本2.0 和更新版本：具備商務用 Skype 系統管理員權力之專屬 Microsoft 365 或 Office 365 帳戶的認證。 <br/>  2.0 以前的版本：具有全域承租人系統管理員權力之專屬 Microsoft 365 或 Office 365 帳戶的認證。 <br/> ||
|啟用參考支援  <br/> |這會定義在主幹設定上啟用或停用 SIP 對您的 IP/PBX 的 SIP 是否有説明。 預設值為 True。 如果 IP/PBX 閘道支援 [參考支援]，請將此設為 True。 否則，必須將此值變更為 False。 如果您不確定您的閘道是否支援參閱，請參閱 [合格的 IP-PBXs 和閘道](../../../SfbPartnerCertification/certification/infra-gateways.md)。   <br/> ||
|EnableFastFailoverTimer  <br/> 版本2.0 和更新版本  <br/> |預設值為 "True" 時，如果閘道不會在10秒內接聽撥出電話，它們會路由傳送至下一個可用的閘道;如果沒有其他主幹，則會自動丟棄通話。  <br/> 不過，在具有慢速網路和閘道回應的組織中，或在建立通話的程式需要超過10秒時，可能會導致通話不必要地中斷。  <br/> 在撥打某些國家/地區的電話時（例如 UAE 或阿富汗），通話建立程式可能需要10秒以上的時間。 如果您遇到類似的問題，您必須將此值變更為 False。 請勿忘記變更所連接的 SBC 或閘道上的對應設定。  <br/> 這個值可以是 True 或 False。 預設值為 True。  <br/> ||
|ForwardCallHistory  <br/> 版本2.0 和更新版本  <br/> | 此參數是用來開啟 SIP 標頭，用來在同時震鈴、來電轉接及來電轉接案例中報告初始來電者。 將參數設定為 True，會開啟兩個 SIP 標頭： <br/>  History-Info <br/>  Referred-By <br/>  History-Info 標頭是用於 retargeting SIP 要求，而「提供 (s) 的標準機制，用來捕獲要求的記錄資訊，以便為網路和使用者啟用多種服務， ([RFC 4244-區段 1.1](http://www.ietf.org/rfc/rfc4244.txt)) 。 若為雲端連接器主幹介面，這會在同時振鈴和來電轉接案例中使用。  <br/>  這個值可以是 True 或 False。 預設值為 False。 <br/> ||
|轉寄 PAI  <br/> 版本2.0 和更新版本  <br/> |PAI 是 SIP 的私人擴充，可讓 SIP 伺服器斷言已驗證使用者的身分識別。 對於 SIP 主幹提供者，如果 History-Info 和 Referred-By 標頭不存在，則 PAI 可能會用於計費目的。 在設定中啟用轉寄 P-Asserted-Identity 時，轉送伺服器會將 SIP &amp; 電話 URI 的 PAI 標頭從雲端連接器轉寄至 SIP 主幹。 轉送伺服器將會轉寄 PAI 標頭，且電話 URI 的 e.164 &amp; 號碼只會在 SIP 主幹與雲端連接器上接收。 轉送伺服器也會轉寄任何方向接收的任何隱私權標頭。 如果轉送伺服器所傳送的 SIP 要求包含表單的隱私權標頭-"隱私權： id" 與 PAI 標頭一起，則宣稱的身分識別應以保密的方式存放在網路信任網域之外。  <br/> 這個值可以是 True 或 False。 預設值為 False。  <br/> ||

### <a name="certificate-requirements"></a>憑證需求
<a name="BKMK_Certs"> </a>

每個 Edge 元件都需要公用憑證授權單位單位的憑證。 憑證必須具有可匯出的私密金鑰，才能在 Edge 元件之間進行複製。 若要符合憑證需求，您必須決定下列選項，並提供憑證的主體名稱 (SN) 和主體替代名稱 (SAN) 。

 **如果您有單一 SIP 網域：**

- **選項1。** 主體名稱必須包含您指派給 Edge 元件的集區名稱。 請注意，因為此名稱是為線上商務用 Skype Edge 元件保留，所以無法 sip.sipdomain.com 主體名稱。 SAN 必須包含 sip.sipdomain.com 和 access Edge 集區的名稱：

  ```console
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain.com,
  acessedgepoolnameforsite1.sipdomain.com
  ```

- **選項2。** 如果您想要在您部署的所有 Edge 集區伺服器上使用單一萬用字元憑證，則可以使用 sipdomain.com 的萬用字元 SAN 專案， \* 而非憑證中的 Edge 集區名稱。 主體名稱可以是您已部署之任何 Edge 集區的 access Edge 集區名稱：

  ```console
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain.com, SAN = *.sipdomain.com
  ```

> [!NOTE]
> 您不能為 sip 建立外部 DNS \<sipdomain\> 專案。因為此名稱屬於 Microsoft 365 或 Office 365 部署，所以為 com。

> [!NOTE]
> 如果您想要針對組織中部署的所有 Edge 集區使用單一憑證，且無法使用在選項2中所定義的通配憑證，則您需要在憑證中包含 SAN 名稱中所有已部署的 Edge 集區的 FQDN。

 **如果您有多個 SIP 網域：**

您將需要為每個 SIP 網域新增 sip.sipdomain.com，以及每個網域的 access Edge 集區名稱 ( 它可以是一個實體集區，但名稱) 不同。 以下是多個 sip 網域案例中的 SN 和 SAN 專案範例：

- **選項1。** 主體名稱必須包含您為 Edge 元件所指派的集區名稱。 請注意，因為此名稱是為線上商務用 Skype Edge 元件保留，所以無法 sip.sipdomain.com 主體名稱。 SAN 必須包含 sip.sipdomain.com 和 access Edge 集區的名稱：

  ```console
  SN = accessedgepoolnameforsite1.sipdomain1.com, SAN = sip.sipdomain1.com, sip.sipdomain2.com,
  acessedgepoolnameforsite1.sipdomain1.com
  ```

- <strong>選項2。</strong>如果您想要在您部署的所有 Edge 集區伺服器上使用單一萬用字元憑證，則可以使用 sipdomain.com 的萬用字元 SAN 專案， \* 而非憑證中的 Edge 集區名稱。 主體名稱可以是您已部署之任何 Edge 集區的 access Edge 集區名稱：

  ```console
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain1.com, sip.sipdomain2.com,
  SAN = *.sipdomain1.com
  ```

> [!NOTE]
> 您不能為 sip 建立外部 DNS \<sipdomain\> 專案。因為此名稱屬於 Microsoft 365 或 Office 365 部署，所以為 com。

針對部署目的，您可以使用下表：

|**選項**|**描述**|**附註**|
|:-----|:-----|:-----|
|您的部署會使用哪個選項？  <br/> |選項1或2  <br/> ||
|錫  <br/> |提供憑證的 SN  <br/> ||
|三  <br/> |為您的憑證提供 SAN  <br/> ||

若要在閘道和轉送伺服器之間使用 TLS，您必須取得指定給閘道之憑證的根憑證或完整憑證鏈。

## <a name="dial-plan-considerations"></a>撥號對應表考慮
<a name="BKMK_DailPlan"> </a>

雲端連接器需要使用線上撥號對應表。 如需如何設定線上撥號對應表的詳細資訊，請參閱 [什麼是撥號對應表？](/microsoftteams/what-are-dial-plans) 
  
## <a name="high-availability-considerations"></a>高可用性考慮
<a name="BKMK_HA"> </a>

當您部署雲端連接器 Edition 以取得高可用性時，您可以部署至少兩個裝置，以做為彼此的備份作用。 每個裝置都包含四個元件： Edge、中繼、中央管理存放區 (CMS) 和網域控制站。

一般情況下，如果裝置中的一個元件已停機，雲端連接器版本可以繼續處理呼叫，但是您必須考慮下列事項：

- **中繼、CMS 和網域控制站元件考慮**

    假設一個裝置中的 CMS 或網域控制站元件停機。 裝置仍可處理撥入和撥出電話，但是如果您在無法存取網域控制站或 CMS 元件時重新開機中繼元件，中繼將無法運作。 當網域控制站停機時，也就是重新開機 CMS 元件。

    **建議：** 重新開機元件之前，請先檢查裝置中其他元件的可用性。

- **Edge 元件考慮**

    如果某個裝置中的 Edge 元件無法使用，則輸入和輸出通話的行為會與下列專案有所不同：

  - 撥 **出電話**-從網際網路向 PSTN 網路撥打的電話。

    雲端中的呼叫散佈機制會識別一部 Edge 元件已停機，而且會將所有呼叫路由傳送至另一個裝置，所以輸出通話成功。

  - 撥 **入呼叫**-從 PSTN 網路呼叫至本機網路或網際網路中的使用者。

     如果接收通話之裝置的 Edge 元件無法正常運作，由於中繼元件無法將呼叫重新導向至其他裝置中的 Edge 元件，所以對此裝置的輸入呼叫將不會成功。

    **建議：** 進行監視系統。 在您找出 Edge 元件的故障之後，請關閉裝置中 Edge 元件無法使用的所有元件。

## <a name="cloud-connector-media-flow"></a>雲端連接器媒體流程
<a name="BKMK_MediaFlow"> </a>

下列圖表概括透過雲端連接器 Edition 進行的輸出和撥出通話流程。 這是瞭解如何建立連線能力的有用資訊。

在第一個圖表中，內部使用者會將撥出電話，如下所示：

1. Dave，使用者位於線上，但是現在在內部網路中，撥打外部 PSTN 使用者的電話。

2. 在線上商務用 Skype 的 SIP 流量路由。

3. 商務用 Skype線上執行號碼的反向號碼查閱。 反向號碼查閱失敗，因為此數位不屬於商務用 Skype 組織中的任何人。

4. 呼叫會路由傳送至 Edge 元件 (透過線上 Edge 的 SIP 和媒體流程，請先進行。媒體會透過內部防火牆) 進入中繼元件。

5. 如果路由存在，Edge 元件會將流量轉送至周邊網路的中繼元件。

6. 轉送元件會將流量傳送至 PSTN 閘道。

![雲端連接器的輸出媒體流程](../../media/c495a2bb-305c-46ef-b16d-b8f9f2b937a8.png)

在下一個圖表中，內部使用者會接收來電，如下所示：

1. PSTN 閘道會接收使用者 Dave 的呼叫，該使用者是在線上，但現在是在內部網路中。

2. SIP 流量會路由傳送至轉送元件。

3. 中繼元件會將 SIP 流量傳送至 Edge 元件，然後商務用 Skype 線上。

4. 商務用 SkypeOnline 會對號碼執行反向號碼查閱，併發現這是使用者 Dave。

5. SIP 信號會進入所有 Dave 的目前狀態點。

6. 媒體流量將會在閘道和中繼元件之間及中繼元件和結束點之間建立。

![雲端連接器的輸入媒體 Flow](../../media/ba5da6f6-e357-43c6-9e8f-4bfdde97c176.png)

## <a name="monitoring-and-troubleshooting"></a>監視和疑難排解
<a name="BKMK_Monitor"> </a>

監視與疑難排解機制會隨每個雲端連接器裝置自動安裝。 此機制會偵測下列事件：

- 雲端連接器裝置的一或多個虛擬機器未連接至內部或網際網路虛擬交換器。

- 一個或多個雲端連接器裝置虛擬機器的狀態為 [已儲存] 或 [停止]。

- 未執行的服務。

  如果偵測到下列其中一項事件，則會耗盡整個雲端連接器裝置，並將其標記為離線狀態，以避免嘗試對無法正常執行的裝置建立呼叫。 雲端連接器自動修復功能會隨後還原服務，並將裝置標示為線上。 若由於某些原因自動復原失敗，請參閱 [疑難排解 Cloud Connector deployment](troubleshoot-your-cloud-connector-deployment.md)。

  - 在中央管理存放區虛擬機器上：

     - 商務用 Skype主要複製器代理程式

     - 商務用 Skype複製副本複製器代理程式

  - 在轉送伺服器虛擬機器上：

     - 商務用 Skype複製副本複製器代理程式

     - 商務用 Skype Server調解

  - 在 Edge Server 虛擬機器上

     - 商務用 Skype複製副本複製器代理程式

     -  商務用 Skype ServerAccess Edge

     - 商務用 Skype ServerAudio/Video Edge

     - 商務用 Skype ServerAudio/Video 驗證

     - 商務用 Skype ServerWeb 會議 Edge

- 已停用轉送伺服器上，「cs RTCSRV」的 Windows 防火牆的輸入規則（「cs RTCMEDSRV」）。

Cloud Connector 2.1 和更新版本支援使用 Operations Management Suite (OMS) 來監視雲端連接器。 如需詳細資訊，請參閱 [使用 Operations Management Suite Monitor Cloud Connector (OMS) ](monitor-cloud-connector-using-operations-management-suite-oms.md)

## <a name="for-more-information"></a>相關資訊
<a name="BKMK_MoreInfo"> </a>

如需詳細資訊，請參閱下列各主題：

- [Microsoft 電話語音解決方案](/microsoftteams/cloud-voice-landing-page)

- [設定及管理商務用 Skype Cloud Connector Edition](configure-skype-for-business-cloud-connector-edition.md)

- [規劃 Cloud Connector Edition 中的媒體旁路](plan-for-media-bypass-in-cloud-connector-edition.md)

- [在雲端連接器 Edition 中部署媒體旁路](deploy-media-bypass-in-cloud-connector.md)
