---
title: 規劃商務用 Skype 雲端連接器版本
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 6ce0e580-8c4a-45de-a54f-e39e438335d6
description: 在商務用 Skype 雲端連接器版本中尋找資訊，這是一組封裝的虛擬機器（Vm），可在 Office 365 （雲端 PBX）中實現與電話系統的內部部署 PSTN 連線。
ms.openlocfilehash: 3b95c1cca24b6faac8a6cf2807b6af324fdc57bd
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002273"
---
# <a name="plan-for-skype-for-business-cloud-connector-edition"></a>規劃商務用 Skype 雲端連接器版本

在商務用 Skype 雲端連接器版本中尋找資訊，這是一組封裝的虛擬機器（Vm），可在 Office 365 （雲端 PBX）中實現與電話系統的內部部署 PSTN 連線。

如果您還沒有已有的 Lync 伺服器或商務用 Skype Server 部署，雲端連接器版本可能是貴組織的正確方案。 如果您仍在調查 Office 365 方案中的哪個電話系統適合您的企業，請參閱[Microsoft 電話方案](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/msft-telephony-solutions)。

本檔說明雲端連接器版本需求和支援的拓撲，並協助您規劃雲端連接器版本部署。 在設定雲端連接器環境之前，請務必閱讀本主題。 當您準備好要部署並設定雲端連接器版本時，請參閱[設定及管理商務用 Skype 雲端連接器版本](configure-skype-for-business-cloud-connector-edition.md)。

雲端連接器版本2.1 現已推出。 如果您尚未升級至2.1，請參閱[升級至新版本的雲端連接器](upgrade-to-a-new-version-of-cloud-connector.md)。 您可以在[https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller)中找到安裝檔。

> [!NOTE]
> Microsoft 支援舊版的雲端連接器版本，在發行新版版本之後的60天。 Microsoft 將支援版本2.0.1 在發行2.1 之後的60天，以允許您升級的時間。 已不再支援2.0.1 之前的所有版本。

雲端連接器版本是一個混合式產品，其中包含一組封裝式虛擬電腦（Vm），可在 Office 365 中使用電話系統與手機系統進行內部部署 PSTN 連線。 在虛擬化的環境中部署最小的商務用 Skype 伺服器拓撲，組織中的使用者可以從 Microsoft 雲端接收 PBX 服務，但 PSTN 連線是透過現有的內部部署語音提供設施.

![拓撲圖顯示將雲端 PBX 連線至商務用 Skype 內部部署的雲端 PBX 閘道。](../../media/bd898e69-6458-4276-aebe-1854f28ed6fa.png)

由於雲端連接器可讓您將 Office 365 服務中的電話系統與您現有的電話環境（例如 PBX、類比裝置和通話中心）整合，因此您可以從現有的電話方案開始將分階段遷移至手機Office 365 中的系統。

例如，假設您的公司有一個複雜的話務中心，有一個 Office 365 中的電話系統無法提供的特定功能。 您可以選擇將話務中心使用者留給現有的解決方案，但將其他使用者移至 Office 365 中的 [電話系統]。

雲端連接器將提供駐留在內部部署和線上的使用者之間的路由，您可以選擇在 Office 365 中將自己的 PSTN 提供者與電話系統搭配使用。

規劃雲端連接器版本部署時，請考慮下列事項：

- 若要使用雲端連接器來利用雲端語音解決方案，您必須註冊在 Office 365 中包含電話系統的 Office 365 租使用者。 如果您還沒有 Office 365 租使用者，您可以在此瞭解如何在此註冊：[商務用 Office 365](https://products.office.com/en-us/business/office)。 請注意，您必須註冊包含商務用 Skype Online 的方案。

- 若要使用商務用 Skype Online 服務註冊雲端連接器裝置，並執行各種 Cmdlet，雲端連接器2.0 及更新版本需要專用的 Office 365 帳戶與商務用 Skype 租使用者管理員許可權。 2.0 之前的雲端連接器版本需要擁有租使用者全域系統管理員許可權的專用 Office 365 帳戶。

- 雲端連接器不需要完整的內部部署商務用 Skype Server 部署。

    目前，雲端連接器不能與 Lync 或商務用 Skype 內部部署伺服器共存。 如果您想要將現有的 Lync 或商務用 Skype 使用者移至 Office 365，並持續提供內部部署的電話給您的使用者，請考慮使用現有的商務用 Skype Server 部署，在 Office 365 中使用 [電話系統] 與內部部署的連線。 如需詳細資訊，請參閱在 office [365 （雲端 PBX）方案中規劃您的電話系統](plan-your-phone-system-cloud-pbx-solution.md)，並[規劃在商務用 Skype Server 中使用內部部署 PSTN 連線的 office 365 中](plan-phone-system-with-on-premises-pstn-connectivity.md)的電話系統。

- 如果您使用的是舊版商務用 Skype 或 Lync Server 部署，且您已延伸架構，只要您已從您的環境中移除所有商務用 Skype 或 Lync Server 元件，就不需要清理雲端連接器部署的架構。

- 您的使用者是在線上。

- 如果您的組織已設定目錄同步處理（DirSync），則必須先在內部部署部署中建立規劃混合式語音的所有使用者帳戶，然後同步處理到雲端。

- 如有需要，您可以保留目前的 PSTN 載波。

- 如果您想要將電話撥入式會議提供給以雲端連接器為宿主的使用者，您可以購買 PSTN 會議授權，或從 Microsoft 開始進行音訊會議優惠支付。

- [音訊會議] 授權（或 [隨選即付] 優惠）也是通話升級所必需的。 如果商務用 Skype 使用者收到來自外部 PSTN 使用者的呼叫，且想要將一個參與者加入該通話（將通話升級至會議），則會透過 Microsoft 音訊會議服務來執行此升級。

- 雲端連接器2.0 及更新版本現在支援媒體旁路。 「媒體旁路」可讓用戶端直接傳送媒體至公用交換式電話網絡（PSTN）的下一個躍點（閘道或會話邊界控制器（SBC）），並從媒體路徑中消除雲端連接器版本元件。 如需詳細資訊，請參閱[在雲端連接器版本中規劃媒體旁路](plan-for-media-bypass-in-cloud-connector-edition.md)。

- 雲端連接器2.1 及更新版本支援使用 Operations Management Suite （OMS）來監視雲端連接器。 如需詳細資訊，請參閱[使用 Operations Management Suite （OMS）監視雲端連接器](monitor-cloud-connector-using-operations-management-suite-oms.md)

- 雲端連接器可用於 Office 365 企業版 E5 的所有國家/地區。

本主題包含下列各節：

- [雲端連接器版本元件](plan-skype-for-business-cloud-connector-edition.md#BKMK_Components)

- [雲端連接器版本拓撲](plan-skype-for-business-cloud-connector-edition.md#BKMK_Topologies)

- [部署需求](plan-skype-for-business-cloud-connector-edition.md#BKMK_Requirements)

- [部署前所需收集的資訊](plan-skype-for-business-cloud-connector-edition.md#BKMK_PlanDeployment)

- [撥號方案考慮](plan-skype-for-business-cloud-connector-edition.md#BKMK_DailPlan)

- [高可用性考慮](plan-skype-for-business-cloud-connector-edition.md#BKMK_HA)

- [雲端連接器媒體流程](plan-skype-for-business-cloud-connector-edition.md#BKMK_MediaFlow)

- [監控和疑難排解](plan-skype-for-business-cloud-connector-edition.md#BKMK_Monitor)

- [如需詳細資訊](plan-skype-for-business-cloud-connector-edition.md#BKMK_MoreInfo)

## <a name="cloud-connector-edition-components"></a>雲端連接器版本元件
<a name="BKMK_Components"> </a>

有了雲端連接器版本，您就會部署一組封裝的 Vm，其中包含最小的商務用 Skype 伺服器拓撲，包括邊緣元件、轉送元件，以及中央管理商店（CMS）角色。 您也會安裝網網域控制站，這是雲端連接器內部正常運作所需的功能。 這些服務是針對包含商務用 Skype Online 服務的 Office 365 租使用者設定的混合式。

![雲端連接器版本元件](../../media/f2d4b8a7-c2f4-4cfc-8137-f187399c1298.png)

雲端連接器元件提供下列功能：

- **Edge 元件**-內部部署拓朴與線上服務之間的通訊會透過邊緣元件進行，其中包括下列元件：

  - **Access Edge** -提供內部部署與商務用 Skype Online 之間的 SIP 路由。

  - **媒體轉送**-提供在轉送式元件與其他媒體端點之間的媒體路由。

  - **媒體轉送驗證/MRAS** -產生可存取媒體轉送的權杖。

- **輸出路由**-提供連線到雲端連接器裝置之閘道或 SBCs 之間的語音流量負載平衡。 通話會平均分割連接至雲端連接器裝置的所有閘道或 SBCs。

    根據原則提供路由至閘道。 僅支援以目的地（輸出） PSTN 數位為基礎的全域原則。

- **中央管理商店（CMS）角色**-包括拓撲元件的配置存放區，包括 CMS 檔案傳輸。

- **中央管理書店（CMS）複本**-從 CMS 角色服務器上的全域 CMS 資料庫同步處理配置資訊。

- **網網域控制站**-雲端連接器 Active Directory 網域服務可儲存部署雲端連接器元件所需的所有全域設定和群組。 系統會針對每個雲端連接器裝置建立一個目錄林。 網網域控制站不能與生產 Active Directory 建立任何連線。 Active Directory 服務包括：

  - Active Directory 網域服務

  - 使用 Active Directory 憑證服務來頒發內部憑證

- **採集轉送元件**-在商務用 SKYPE 和 PSTN 閘道之間實現 SIP 及媒體閘道對應通訊協定。 包含一個 CMS 複本，可同步處理全域 CMS 資料庫的配置。

## <a name="cloud-connector-edition-topologies"></a>雲端連接器版本拓撲
<a name="BKMK_Topologies"> </a>

出於此討論的目的，我們將會參考 PSTN 網站。 PSTN 網站是雲端連接器裝置的組合，可在相同的位置部署，以及與其連接的常見 PSTN 閘道。 PSTN 網站可讓您：

- 提供與使用者最接近的閘道連線。

- 在一或多個 PSTN 網站中部署多個雲端連接器裝置，以提供可伸縮性。

- 在單一 PSTN 網站中部署多個雲端連接器裝置，以允許高可用性。

本主題介紹 PSTN 網站。 如需規劃 PSTN 網站的詳細資訊，請參閱[雲端連接器版本 PSTN 網站的規劃](plan-for-cloud-connector-edition-pstn-sites.md)。

您可以部署下列雲端連接器拓撲：

- 每個 PSTN 網站有單一雲端連接器 Edition 裝置。 此拓撲僅適用于評估目的，因為它不提供高可用性。

- 每個 PSTN 網站有多個雲端連接器 Edition 裝置，以提供高可用性。

- 含多個雲端連接器 Edition 裝置的多個 PSTN 網站，可提供高可用性的可伸縮性。 您最多可以部署200網站。

規劃拓撲時，請考慮下列事項：

- 有了雲端連接器2.0 及更新版本，一個 PSTN 網站最多可以有16個雲端連接器裝置。 舊版版本最多支援每個網站4個裝置。

- 使用雲端連接器測試的硬體設定有兩種類型：

  - 較大的版本可以處理大量同時通話，且在所有類型的生產環境中都受支援。

  - 較小的版本是要在低端硬體上執行，而且可用於評估用途，或適用于呼叫量較低的網站。 如果您部署的是較小版本的雲端連接器，您仍然需要警惕生產類別的硬體需求（例如雙電源）。

- 如果您有雲端連接器版本2.0 或更新版本，且您部署16個裝置的最大設定（較大的硬體），則您的 PSTN 網站可以處理多達8000個同時通話。 如果您部署較小的版本，支援的限制是800。

    您也需要將某些裝置專用於高可用性。 最小的建議是將一個裝置保留為高可用性。

  - 在版本2中，如果您要部署 15 + 1 設定，您的 PSTN 網站可以處理多達7500同時通話。

  - 如果您有較舊的版本，且部署的 3 + 1 （含較大的硬體）最大值，您的 PSTN 網站就能處理多達1500同時通話。 如果您部署較小的版本，支援的限制是150。

-  如果您需要針對每個 PSTN 網站進行更多通話，您可以在同一個位置部署其他 PSTN 網站來擴大。

> [!NOTE]
> 除非另行說明，否則下面的圖表和範例會假設使用較大版本的雲端連接器。

### <a name="single-cloud-connector-appliance-within-a-single-pstn-site"></a>單一 PSTN 網站內的單一雲端連接器裝置

下圖顯示單一 PSTN 網站內的單一雲端連接器 Edition 裝置。 請注意，「雲端連接器」是由在周邊網路中的一個物理主機電腦上安裝的四個 Vm 所組成，以進行安全性。

![單一雲端連接器與一個 PSTN 網站](../../media/7ffe6953-8c66-4323-940e-cd2e6c3c2a66.png)

### <a name="multiple-cloud-connector-appliances-within-a-single-pstn-site"></a>單一 PSTN 網站中有多個雲端連接器裝置

 針對可伸縮性和高可用性用途，您可以選擇在單一 PSTN 網站中使用多個雲端連接器版本，如下圖所示。 請考慮下列事項：

- 通話會以隨機順序散佈在一個池中的雲端連接器之間。

- 針對容量規劃目的，您必須考慮根據下列計算，在一個或多個雲端連接器離線時處理負載的能力：

  - **N + 1 個方塊。** 對於較大版本的雲端連接器，N + 1 盒支援 500\*N 個與99.8% 可用性的並行呼叫。

    如果是較小的雲端連接器版本，則 N + 1 方塊\*支援 50 N 個併發呼叫99.8% 的可用性。

  - **N + 2 個方塊。** 對於較大版本的雲端連接器，N + 2 方塊支援 500\*N 個併發呼叫99.9% 的可用性。

    如果您的雲端連接器較小，N + 2 方塊支援 50\*N 個併發呼叫，且可用性99.9%。

![1 PSTN 網站內的兩個雲端連接器](../../media/fc0dc47f-5595-42cb-9432-9c8ff3e134e9.png)

### <a name="multiple-pstn-sites-with-one-or-more-cloud-connectors-per-site"></a>每個網站有一個或多個雲端連接器的多個 PSTN 網站

您也可以選擇在每個網站中使用一個或多個雲端連接器版本的多個 PSTN 網站。 如果您的 PSTN 網站達到同時通話的限制，您可以新增另一個 PSTN 網站來處理這項負載。

多個 PSTN 網站也可讓您提供最接近您使用者之閘道的連線能力。 例如，假設您有位於西雅圖和阿姆斯特丹的 PSTN 閘道。 您可以部署兩個 PSTN 網站（一個位於西雅圖，一個在阿姆斯特丹中），並指派使用者使用與其最接近的 PSTN 網站。 西雅圖的使用者會傳送到西雅圖 PSTN 網站和閘道，而將阿姆斯特丹中的使用者路由到阿姆斯特丹 PSTN 網站和閘道：

![2個 PSTN 網站內的雲端連接器版本](../../media/16ead6d3-67da-4e71-b4d5-d895b4c9384e.png)

## <a name="requirements-for-deployment"></a>部署需求
<a name="BKMK_Requirements"> </a>

在您部署雲端連接器版本之前，請確定您的環境具備下列各項：

- **針對主機電腦-** 雲端連接器 Vm 必須部署在執行 Windows Server 2012 R2 資料中心版（英文）且已啟用 Hyper-v 角色的專用硬體上。

    針對版本2.0 及更新版本，系結到商務用 Skype 企業版交換器的主機電腦網卡，必須在與雲端連接器公司網路電腦相同的子網中設定 IP 位址。

- 針對版本2.1 及更新版本，主機裝置必須安裝 .NET Framework 4.6.1 或更新版本。

- **針對虛擬電腦-** Windows Server 2012 R2 ISO （英文）影像（.iso）。 ISO 會轉換為將執行商務用 Skype 雲端連接器版本的虛擬機器的 Vhd。

- 支援在您部署中的每個雲端連接器版本安裝4個 Vm 的必要硬體。 建議使用下列設定：

  - 64位雙處理器、六核（12個真實核心）、2.50 十億位元（GHz）或更高版本

  - 64千百萬位元組（英國） ECC RAM

  - 4 600 GB （或更好的） 10K RPM 128M 快取 RPM，在 RAID 5 配置中設定的磁片6Gbps 磁片

  - 3個 1 Gbps RJ45 高輸送量網路介面卡

- 如果您選擇部署的雲端連接器版本較小且支援多達50同時通話，您將需要下列硬體：

  - 英特爾 i7 4790 四核含英特爾4600圖形（不需要高端圖形）

  - 32 GB DDR3-1600 非 ECC

  - 2：在 RAID 0 中，1TB 7200RPM SATA III （6 Gbps）

  - 2: 1 Gbps 乙太網路（RJ45）

- 如果要流覽網際網路的主機電腦需要有 proxy 伺服器，您必須進行下列設定變更：

  - 若要略過 proxy，請指定您的 proxy 伺服器所設定的 WinHTTP Proxy 設定，以及包含 "192.168.213] 的旁路清單。\*「您的雲端連接器 Managements 服務和商務用 Skype 網上的網路使用的網路，如您的 CloudConnector 檔案中所定義。 否則，管理連線將會失敗，並會阻止雲端連接器的部署和自動復原。 以下是 winHTTP 配置命令的範例： netsh winHTTP 設定 proxy "10.10.10.175： 8080" 旁路-list = "\*local; 1。\*; 172.20。\*; 192.168.218。\*[\<本機\>]。

  - 指定每個電腦的 proxy 設定，而不是每個使用者。 否則雲端連接器下載將會失敗。 您可以在每一台電腦上使用註冊表變更或群組原則設定來指定 proxy 設定，如下所示：

  - **Registry：** HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\Windows\CurrentVersion\Internet 設定] ProxySettingsPerUser dword：00000000

  - [**群組原則]：** 電腦\>系統管理\>範本 Windows\>元件 Internet Explorer：針對每個電腦建立 Proxy 設定（而不是每個使用者）

- 合格的 PBX/主幹或合格的 SBC/閘道（建議至少使用兩個閘道）。

    雲端連接器支援與商務用 Skype 認證的相同會話邊界控制器（SBCs）。 如需詳細資訊，請參閱[商務用 Skype 的電話結構](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways)。

- 本機伺服器系統管理員帳戶，擁有在主機伺服器上安裝和設定 Hyper-v 的許可權。 帳戶必須在安裝並設定 Hyper-v 的本機伺服器上擁有系統管理員許可權。

- 在部署期間，系統會要求您建立具備在雲端連接器網域中建立併發布拓撲的網域系統管理員帳戶。

- 在安裝套件隨附的 CloudConnector 檔案中定義的外部 DNS 記錄：

  - Edge 元件存取邊緣服務的外部 DNS 記錄例如，[ap]\<是 [\>功能變數名稱]。 每個 PSTN 網站都需要一個記錄。 此記錄必須包含該網站所有邊緣的 IP 位址。

- 已建立所有必要的 DNS 和 SRV 記錄的 Office 365 租使用者。

    > [!IMPORTANT]
    > 當您將租使用者與雲端連接器版本整合時，不支援使用預設網域尾碼（onmicrosoft.com）作為貴組織的 SIP 網域。 > 您無法使用 sip。\<功能變數名稱\>做為雲端連接器 Edge 訪問 proxy 介面的名稱，因為此 DNS 記錄是由 Office 365 使用。

- 從公用憑證授權單位（CA）取得之外部邊緣的憑證。

- 允許透過所需埠的流量已完成的防火牆規則。

- 主機與虛擬機器的網際網路連線。 雲端連接器會從網際網路下載部分軟體;因此，您必須提供閘道和 DNS 伺服器資訊，才能讓雲端連接器主機電腦和 Vm 連線至網際網路並下載必要的軟體。

- 安裝在主機電腦上的租使用者遠端 PowerShell 模組。

- Office 365 商務用 Skype 系統管理員認證，可執行遠端 PowerShell。

    > [!IMPORTANT]
    > 系統管理員帳戶不能啟用多重要素驗證。

> [!NOTE]
> 只有 Microsoft Hyper-v 虛擬化平臺支援雲端連接器部署。 不支援其他平臺（例如 VMware 和 Amazon Web 服務）。

> [!NOTE]
> 執行雲端連接器的最低硬體指導方針是以基本硬體容量（核心、MHz、千百萬位元組等）為基礎，且在任何電腦的體系結構中都是以適合無形效能障礙的部分緩衝區為基礎。 Microsoft 已在商業上可用的硬體上執行最差的案例負載測試。 已驗證媒體質量與系統效能。 官方雲端連接器裝置合作夥伴的 Microsoft 擁有特定的雲端連接器硬體實施方案，它們可獨立測試效能，而且其硬體適用性必須符合負載和品質需求。

> [!NOTE]
> AudioCodes 和 Sonus 產生的裝置已修改程式碼，且在 Windows Server 標準版伺服器上執行。 支援這些裝置。

## <a name="information-you-need-to-gather-before-deployment"></a>部署前所需收集的資訊
<a name="BKMK_PlanDeployment"> </a>

開始進行部署之前，您必須先判斷您的部署大小、正在處理的 SIP 網域，以及規劃要部署之每個 PSTN 網站的設定資訊。 首先，您將：

- 根據您公司中使用的 SIP Uri，找出此部署所提供的所有 SIP 網域。

- 判斷您需要部署的 PSTN 網站數目。

- 請確定您具備支援四個您要為每個雲端連接器版本安裝的虛擬機器所需的硬體。

針對您打算部署的每個 PSTN 網站，您必須：

- 針對每個雲端連接器裝置中的所有元件建立名稱（請參閱[決定部署參數](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams)）。

- 定義埠範圍（請參閱[埠和通訊協定](plan-skype-for-business-cloud-connector-edition.md#BKMB_Ports)）。

- 建立邊緣元件的外部 DNS 記錄（請參閱[部署需求](plan-skype-for-business-cloud-connector-edition.md#BKMK_Requirements)）。

- 判斷您的邊緣元件的憑證需求（請參閱[證書需求](plan-skype-for-business-cloud-connector-edition.md#BKMK_Certs)）。

### <a name="ports-and-protocols"></a>連接埠和通訊協定
<a name="BKMB_Ports"> </a>

定義媒體埠範圍時，請注意下列事項：

- 用戶端總是將埠範圍50000用於媒體流量的50019，此範圍是在商務用 Skype Online 中預先定義的，而且無法變更。

- 根據預設，轉送器元件會將埠範圍 49 152 用於媒體流量的 57 500。 不過，連線是透過內部防火牆建立的，而且出於安全性考慮，您可以在您的拓撲中限制這個埠範圍。 每次通話最多需要4個埠。 如果您想要限制轉送元件與 PSTN 閘道之間的埠數，您也需要在閘道上設定對應的埠範圍。

- 您必須在周邊網路中部署雲端連接器。 這表示您會有兩個防火牆：

  - 第一個防火牆在網際網路和您的周邊網路之間是外部的。

  - 第二個防火牆在周邊網路和您的內部網路之間是內部的。

    您的用戶端可以在網際網路或內部網路中：

  - 網際網路中的用戶端會透過邊緣元件透過外部防火牆連線至您的 PSTN。

  - 內部網路中的用戶端會透過內部防火牆連線到周邊網路中的流量分配元件，這會將流量連接至 SBC 或 PSTN 閘道。

    這表示您需要在兩個防火牆中開啟埠。

下表說明外部與內部防火牆的埠與埠範圍。

下表顯示啟用內部網路和轉送作業中用戶端之間通訊的埠與埠範圍：

**內部防火牆**



|**來源 IP**|**目的地 IP**|**來源埠**|**目的地埠**|
|:-----|:-----|:-----|:-----|
|雲端連接器轉送元件  <br/> |SBC/PSTN 閘道  <br/> |每  <br/> |TCP 5060\*\*  <br/> |
|SBC/PSTN 閘道  <br/> |雲端連接器轉送元件  <br/> |每  <br/> |TCP 5068/TLS 5067  <br/> |
|雲端連接器轉送元件  <br/> |SBC/PSTN 閘道  <br/> |UDP 49 152-57 500  <br/> |每\*\*\*  <br/> |
|SBC/PSTN 閘道  <br/> |雲端連接器轉送元件  <br/> |每\*\*\*  <br/> |UDP 49 152-57 500  <br/> |
|雲端連接器轉送元件  <br/> |內部用戶端  <br/> |TCP 49 152-57 500\*  <br/> |TCP 50000-50019  <br/> 可選  <br/> |
|雲端連接器轉送元件  <br/> |內部用戶端  <br/> |UDP 49 152-57 500\*  <br/> |UDP 50000-50019  <br/> |
|內部用戶端  <br/> |雲端連接器轉送元件  <br/> |TCP 50000-50019  <br/> |TCP 49 152-57 500\*  <br/> |
|內部用戶端  <br/> |雲端連接器轉送元件  <br/> |UDP 50000-50019  <br/> |UDP 49 152-57 500\*  <br/> |

\*這是轉送元件上的預設埠範圍。 針對最佳通話流程，需要每個通話有四個埠。

\*\*此埠必須在 SBC/PSTN 閘道進行設定;5060是一個範例。 您可以在 SBC/PSTN 閘道設定其他埠。

\*\*\*請注意，如果 SBC/閘道製造商允許，您也可以限制您 SBC/閘道的埠範圍。

為安全起見，您可以使用[CsMediationServer](https://docs.microsoft.com/powershell/module/skype/set-csmediationserver?view=skype-ps) Cmdlet 來限制轉送器元件的埠範圍。

例如，下列命令會限制轉送元件將在 50 000-51 000 for audio （內和向外）使用的埠數。 採集轉送元件將能使用此設定來處理250同時進行的呼叫。 請注意，您也可能想要在 SBC/PSTN 閘道限制此範圍：

```powershell
Set-CSMediationServer -Identity MediationServer:mspool.contoso.com -AudioPortStart 50000 - AudioPortCount 1000
```

若要取得轉送元件的名稱並查看預設埠，您可以使用[CsService](https://docs.microsoft.com/powershell/module/skype/get-csservice?view=skype-ps) Cmdlet，如下所示：

```powershell
Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount
```

下表顯示啟用雲端連接器邊緣元件與外部防火牆之間通訊的埠與埠範圍。 下表顯示最小建議。

在這種情況下，網際網路的所有媒體流量都會透過線上邊緣來流動，如下所示：使用者端點\>--線上邊緣\>--雲端連接器邊緣：

**外部防火牆-最低設定**



|**來源 IP**|**目的地 IP**|**來源埠**|**目的地埠**|
|:-----|:-----|:-----|:-----|
|每  <br/> |雲端連接器邊緣外部介面  <br/> |每  <br/> |TCP （MTLS）5061  <br/> |
|雲端連接器邊緣外部介面  <br/> |每  <br/> |每  <br/> |TCP （MTLS）5061  <br/> |
|雲端連接器邊緣外部介面  <br/> |每  <br/> |每  <br/> |TCP 80  <br/> |
|雲端連接器邊緣外部介面  <br/> |每  <br/> |每  <br/> |UDP 53  <br/> |
|雲端連接器邊緣外部介面  <br/> |每  <br/> |每  <br/> |TCP 53  <br/> |
|雲端連接器邊緣外部介面  <br/> |每  <br/> |UDP 3478  <br/> |UDP 3478  <br/> |
|每  <br/> |雲端連接器邊緣外部介面  <br/> |TCP 50000-59999  <br/> |TCP 443  <br/> |
|每  <br/> |雲端連接器邊緣外部介面  <br/> |UDP 3478  <br/> |UDP 3478  <br/> |
|雲端連接器邊緣外部介面  <br/> |每  <br/> |TCP 50000-59999  <br/> |TCP 443  <br/> |

下表顯示啟用雲端連接器邊緣元件與外部防火牆之間通訊的埠與埠範圍。 下表顯示建議的解決方案。

在這種情況下，internet 終點的所有媒體流量都可以直接流向雲端連接器邊緣元件。 媒體路徑將是使用者端點-\>雲端連接器邊緣。

> [!NOTE]
> 如果使用者的結束點位於對稱 NAT 之後，此解決方案將無法運作。

**外部防火牆-建議的設定**


|**來源 IP**|**目的地 IP**|**來源埠**|**目的地埠**|
|:-----|:-----|:-----|:-----|
|每  <br/> |雲端連接器邊緣外部介面  <br/> |每  <br/> |TCP （MTLS）5061  <br/> |
|雲端連接器邊緣外部介面  <br/> |每  <br/> |每  <br/> |TCP （MTLS）5061  <br/> |
|雲端連接器邊緣外部介面  <br/> |每  <br/> |每  <br/> |TCP 80  <br/> |
|雲端連接器邊緣外部介面  <br/> |每  <br/> |每  <br/> |UDP 53  <br/> |
|雲端連接器邊緣外部介面  <br/> |每  <br/> |每  <br/> |TCP 53  <br/> |
|雲端連接器邊緣外部介面  <br/> |每  <br/> |TCP 50000-59999  <br/> |每  <br/> |
|雲端連接器邊緣外部介面  <br/> |每  <br/> |UDP 3478;UDP 50000-59999  <br/> |每  <br/> |
|每  <br/> |雲端連接器邊緣外部介面  <br/> |每  <br/> |TCP 443;TCP 50000-59999  <br/> |
|每  <br/> |雲端連接器邊緣外部介面  <br/> |每  <br/> |UDP 3478;UDP 50000-59999  <br/> |

### <a name="host-internet-connectivity-requirements"></a>主機網際網路連線需求
<a name="BKMB_Ports"> </a>

主機電腦必須能夠存取外部資源，才能成功安裝、更新及管理雲端連接器。 下表顯示主機機與外部資源之間所需的目的地和埠。

|發展  <br/> |來源 IP  <br/> |目的地 IP  <br/> |來源埠  <br/> |目的地埠  <br/> |通訊協定  <br/> |特殊  <br/> |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|發  <br/> |雲端連接器主機 Ip  <br/> |每  <br/> |每  <br/> |53  <br/> |TCP/UDP  <br/> |DNS  <br/> |
|發  <br/> |雲端連接器主機 Ip  <br/> |每  <br/> |每  <br/> |80、443  <br/> |TCP-OUT  <br/> |憑證撤銷清單（CRL）  <br/> |
|發  <br/> |雲端 Connectorr 主機 Ip  <br/> |每  <br/> |每  <br/> |80、443  <br/> |TCP-OUT  <br/> |雲端連接器更新  <br/> 商務用 Skype Online  <br/> 管理 PowerShell  <br/> Windows Update  <br/> |

如果需要更嚴格的規則，請參閱下列 whitelisting Url：

- [Office 365 url 和 IP 位址範圍](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US)中的[憑證吊銷清單 url](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)

- Windows Update：[如何為軟體更新設定防火牆](https://technet.microsoft.com/en-us/library/bb693717.aspx)

- 商務用 Skype Online 系統管理 PowerShell \*：. online.lync.com

    如果您需要此目的地的 proxy 排除，您需要將它新增至 WinHTTP 旁路清單。

- 雲端連接器更新：[下載中心](https://aka.ms/CloudConnectorInstaller)、 [https://go.microsoft.com](https://go.microsoft.com)和[https://download.microsoft.com](https://download.microsoft.com)

### <a name="dns-name-resolution-for-the-edge-component"></a>Edge 元件的 DNS 名稱解析
<a name="BKMB_Ports"> </a>

Edge 元件需要解析 Office 365 服務的外部名稱，以及其他雲端連接器元件的內部名稱。

每個邊緣元件都是具有外部與內部介面的多穴電腦。 雲端連接器會在周邊網路中的網網域控制站元件上部署 DNS 伺服器。 您可以將 Edge 伺服器指向週邊伺服器中的 DNS 伺服器，以進行所有名稱解析，但您需要啟用雲端連接器 DNS 伺服器來解析外部名稱，方法是設定包含一或多個引用名稱之外部查詢之 DNS A 記錄的 DNS 區域查閱其他公用 DNS 伺服器。

在 .ini 檔案中，如果您要從與 SIP 網域相同的網域空間將閘道的 FQDN 名稱設定為，則會在週邊的 DNS 伺服器中建立此 SIP 網域的權威性區域。 如果 Edge 伺服器指向這個 DNS 伺服器來解析名稱，則 Edge 將永遠無法解析 _sipfederationtls。\<yourdomain\> DNS 記錄，這是通話流程所必需的。 在這種情況下，Microsoft 建議您在 Edge 外部介面上提供 DNS 伺服器，以解析網際網路名稱查閱，而且每個 Edge 元件都必須使用主機檔案將其他雲端連接器元件名稱解析為 IP 位址。

> [!NOTE]
> 出於安全考慮，我們建議您不要將雲端連接器 DNS 伺服器指向生產網域中的內部伺服器以進行名稱解析。

### <a name="determine-deployment-parameters"></a>判斷部署參數
<a name="BKMK_SiteParams"> </a>

首先，您必須定義下列常見的部署參數：


|**選項**|**描述**|**筆記**|
|:-----|:-----|:-----|
|SIP 網域  <br/> |公司使用者正在使用 SIP URI。 提供此部署所提供的所有 SIP 網域。 您可以有一個以上的 SIP 網域。  <br/> ||
|PSTN 網站數量  <br/> |您將部署的 PSTN 網站數目。  <br/> ||

針對您規劃要部署的每個 PSTN 網站，您必須先收集下列資訊，才能開始部署。 更新 CloudConnector 檔案時，您將需要提供此資訊。

配置閘道資訊時，請記住下列事項：

- 如果您只有一個閘道，請移除第二個閘道的 .ini 檔案中的節。 如果有多個閘道，請遵循現有的格式來新增。

- 確認閘道的 IP 位址與埠正確無誤。

- 若要支援 PSTN 閘道層級 HA，請保留副閘道或新增其他閘道。

可選若要限制撥出電話號碼，請更新 LocalRoute 值。



|**網站參數**|**描述**|**筆記**|
|:-----|:-----|:-----|
|虛擬電腦網功能變數名稱稱  <br/> |雲端連接器內部元件的功能變數名稱。 這個網域必須不同于生產網域。 所有雲端連接器裝置上的名稱必須相同。  <br/> 在 .ini 檔案中的名稱： "VirtualMachineDomain"  <br/> |. 本地域是可取的。  <br/> |
|雲端連接器網網域控制站名稱  <br/> |網網域控制站的名稱。  <br/> 在 .ini 檔案中的名稱： "ServerName"  <br/> |必須小於或等於15個字元。 輸入 [僅 Netbios 名稱]。  <br/> |
|雲端連接器網網域控制站 IP/子網路遮罩  <br/> |網網域控制站的 IP 位址。  <br/> 在 .ini 檔案中的名稱： "IP"  <br/> ||
|O365 Online 服務 Fqdn  <br/> |在大多數情況下，都必須是世界範圍的 O365 實例的預設值。  <br/> 在 .ini 檔案中的名稱： "OnlineSipFederationFqdn"  <br/> ||
|名  <br/> |商務用 Skype 網站名稱;例如，北京。  <br/> .Ini 檔案中的名稱： "SiteName"  <br/> 針對版本1.4.1 及更新版本，每個網站的網站名稱必須不同，而且名稱必須符合 PSTN 網站（如果存在的話），並在 Office 365 中定義。 請注意，當您在網站中註冊第一個裝置時，系統會自動建立 PSTN 網站。  <br/> ||
|HardwareType  <br/> 發行1.4.1 及更新版本  <br/> |硬體類型。 預設值為 Normal。 您也可以設定為 [最小值]。  <br/> ||
|國家/地區代碼  <br/> |撥號的國家/地區碼。  <br/> 在 .ini 檔案中的名稱： "CountryCode"  <br/> ||
|座  <br/> |城市（選用）。  <br/> 在 .ini 檔案中的名稱： "City"  <br/> ||
|市  <br/> |State （選用）。  <br/> 在 .ini 檔案中的名稱： "State"  <br/> ||
|基底 VM IP 位址  <br/> |將用來建立所有雲端連接器虛擬機器的 VHDX 之暫時基底 VM 的 IP 位址。 這個 IP 必須在下一個步驟中定義的周邊網路子網，且需要網際網路存取。 請務必定義企業預設閘道以及可路由至網際網路的 DNS。  <br/> 在 .ini 檔案中的名稱： "BaseVMIP"  <br/> ||
|WSUSServer  <br/> WSUSStatusServer  <br/> 發行1.4.1 及更新版本  <br/> |Windows Server Update Services （WSUS）的位址（即內部網路伺服器），以從 Microsoft Update 託管更新。  <br/> 如果不需要 WSUS，您可以保留空白。  <br/> ||
|內部網路的子網路遮罩  <br/> |雲端連接器會為雲端連接器元件之間的內部通訊設定 IP 網路。 Edge 也必須連線到另一個允許網際網路連線的子網。  <br/> .Ini 檔案中的名稱： "CorpnetIPPrefixLength" 在 [VM 網路池的參數] 下  <br/> ||
|外部網路的子網路遮罩  <br/> |針對 Edge 元件的外部網路。  <br/> .Ini 檔案中的名稱： "InternetIPPrefix" 在 [VM 網路池的參數] 下  <br/> ||
|內部網路的切換名稱  <br/> |將用於內部雲端連接器網路的切換名稱。  <br/> 在大多數情況下，您可以使用預設建議的值。  <br/> 在 .ini 檔案中的名稱： "CorpnetSwitchName" 在 VM 網路池的 [參數] 底下  <br/> ||
|外部網路的切換名稱  <br/> |將用於外部雲端連接器網路的開關名稱。  <br/> 在大多數情況下，您可以使用預設建議的值。  <br/> 在 .ini 檔案中的名稱： "InternetSwitchName" 在 VM 網路池的 [參數] 底下  <br/> ||
|內部網路的預設閘道  <br/> |此閘道必須提供網際網路接入權（網際網路也需要設定 DNS 伺服器），並將在雲端連接器元件的內部介面進行設定。  <br/> 在 .ini 檔案中的名稱： "CorpnetDefaultGateway" 在 VM 網路池的 [參數] 底下  <br/> ||
|Edge 元件外部介面的預設閘道  <br/> |將在 Edge 元件的外部介面上進行設定。  <br/> 在 .ini 檔案中的名稱： "InternetDefaultGateway" 在 VM 網路池的 [參數] 底下  <br/> ||
|內部網路的 DNS 伺服器  <br/> |將在臨時 VM 的內部介面上設定。 必須為網際網路名稱提供名稱解析。 如果沒有提供 DNS 伺服器，網際網路連線將會失敗，而且無法完成部署。  <br/> 在 .ini 檔案中的名稱： "CorpnetDNSIPAddress" 在 VM 網路池的 [參數] 底下  <br/> ||
|[邊緣] 元件外部介面的 DNS 伺服器  <br/> |將在邊緣的外部介面進行設定。  <br/> 在 .ini 檔案中的名稱： "InternetDNSIPAddress" 在 VM 網路池的 [參數] 底下  <br/> ||
|管理開關名稱  <br/> |管理開關是一個會自動建立的暫時開關，在部署期間將用來配置雲端連接器。 部署之後，就會自動中斷連線。 它必須是與雲端連接器中所使用的任何其他網路不同的子網。  <br/> 在大多數情況下，您可以使用預設建議的值。  <br/> 在 .ini 檔案中的名稱： "ManagementSwitchName" 在 VM 網路池的 [參數] 底下  <br/> ||
|管理子網位址/子網路遮罩  <br/> |管理子網是一個會自動建立的臨時子網，在部署期間將用來配置雲端連接器。 部署之後，就會自動移除該檔案。 它必須是與雲端連接器中所使用的任何其他網路不同的子網。  <br/> 在 .ini 檔案中的名稱： "ManagementIPPrefix" 和 "ManagementIPPrefixLength" 在 VM 網路池的 [參數] 底下  <br/> ||
|中央管理商店（CMS）電腦  <br/> |用於中央管理書店（CMS）的單一 FQDN。 AD 功能變數名稱將用來產生 FQDN。  <br/> 在 .ini 檔案中的名稱： "ServerName" 位於主要中央管理服務的參數下  <br/> |必須小於或等於15個字元。 輸入 [僅 Netbios 名稱]。  <br/> （CMS 池名稱 = 伺服器名稱）  <br/> |
|CMS 電腦 IP 位址  <br/> |CMS 伺服器的 IP 位址（在周邊網路內部）。  <br/> INI 檔案中的名稱： "IP" 位於主要中央管理服務的參數下方  <br/> ||
|檔案共用名稱稱  <br/> |要在 CMS 伺服器上針對商務用 Skype 複製資料建立的檔案共用名稱稱（例如，CmsFileStore）。  <br/> 在大多數情況下，您可以使用預設建議的值。  <br/> 在 .ini 檔案中的名稱： "CmsFileStore" 在主要中央管理服務的參數下  <br/> ||
|採集轉送元件池名稱  <br/> |仲介元件的 [池名稱]。 輸入 [僅 Netbios 名稱]。 AD 功能變數名稱將用來產生 FQDN。  <br/> 在 .ini 檔案中的名稱： "PoolName" 在 [中繼伺服器池的參數] 下  <br/> |必須小於或等於15個字元。 輸入 [僅 Netbios 名稱]。  <br/> |
|轉送轉送元件名稱  <br/> |轉送元件1的元件名稱。 輸入 [僅 Netbios 名稱]。 AD 功能變數名稱將用來產生 FQDN。  <br/> 在 .ini 檔案中的名稱： "ServerName" （在 [中繼伺服器池的參數] 下）  <br/> |必須小於或等於15個字元。 輸入 [僅 Netbios 名稱]。  <br/> |
|採集轉送元件電腦 IP 位址  <br/> |仲介元件的內部網路網路 IP （在周邊網路內）。  <br/> 在 .ini 檔案中的名稱： "IP" 位於 [中繼伺服器池的參數] 底下  <br/> ||
|Edge 池內名稱  <br/> |Edge 元件的 [池名稱]。 輸入 [僅 Netbios 名稱]。 AD 功能變數名稱將用來產生 FQDN。  <br/> .Ini 檔案中的名稱： "InternalPoolName" 在 [Edge 伺服器池的參數] 下  <br/> |必須小於或等於15個字元。 輸入 [僅 Netbios 名稱]。  <br/> |
|Edge 伺服器內部名稱  <br/> |Edge 元件的元件名稱。 輸入 [僅 Netbios 名稱]。 AD 功能變數名稱將用來產生 FQDN。  <br/> .Ini 檔案中的名稱： "InternalServerName" 在 [Edge 伺服器池的參數] 下  <br/> |必須小於或等於15個字元。 輸入 [僅 Netbios 名稱]。  <br/> |
|Edge 伺服器內部 IP  <br/> |Edge 元件的內部周邊網路 IP，以與雲端連接器的其他元件進行通訊。  <br/> .Ini 檔案中的名稱： "InternalServerIPs" 在 [Edge 伺服器池的參數] 下  <br/> ||
|存取池外部名稱  <br/> |存取邊緣的名稱;例如，[AP]。 這個名稱必須與提供給 SSL 憑證的名稱相符。 輸入 [僅 Netbios 名稱]。 SIP 功能變數名稱將用來產生 FQDN。 一個外部池名稱將用於池中的所有邊緣元件。 每個 PSTN 網站都需要一個 Edge 存取池。  <br/> .Ini 檔案中的名稱： "ExternalSIPPoolName" 在 [Edge 伺服器池的參數] 下  <br/> |必須小於或等於15個字元。 輸入 [僅 Netbios 名稱]。  <br/> 「sip」是保留的，因此無法用來做為名稱。  <br/> 產生的 FQDN 名稱必須與提供給 SSL 憑證的名稱相符。  <br/> |
|存取邊緣的外部 IP  <br/> |Edge 元件的外部 IP-如果沒有可用的 NAT，則為公用 IP，或是已翻譯的 IP （如果已映射的話，請指定兩個位址）。  <br/> .Ini 檔案中的名稱： "ExternalSIPIPs" 在 [Edge 伺服器池的參數] 下  <br/> ||
|媒體繼電器名稱  <br/> |音訊視頻媒體轉送邊緣的名稱;例如，MR。 一個外部池名稱將用於池中的所有邊緣元件。 每個 PSTN 網站都需要一個 Edge 媒體轉送池。  <br/> .Ini 檔案中的名稱： "ExternalMRFQDNPoolName" 在 [Edge 伺服器池的參數] 下  <br/> |必須小於或等於15個字元。 輸入 [僅 Netbios 名稱]。  <br/> |
|媒體轉送邊緣的外部 IP  <br/> |目前只支援一個 IP，所以這會與存取邊緣相同，也就是公用或對應的 IP （如果已對應的話，請指定兩個位址）。 可以是與存取邊緣的邊緣元件外部 IP 相同的位址。 注意如果 Edge 位於 NAT 之後，您也必須指定下一個參數的值。  <br/> .Ini 檔案中的名稱： "ExternalMRIPs" 在 [Edge 伺服器池的參數] 下  <br/> ||
|媒體轉送邊緣的外部 IP （如果邊緣位於 NAT 之後）  <br/> |如果您的邊緣位於 NAT 之後，您也需要指定 NAT 裝置的公用位址。  <br/> .Ini 檔案中的名稱： "ExternalMRPublicIPs" 在 [Edge 伺服器池的參數] 下  <br/> ||
|語音閘道1品牌與型號  <br/> |指定 SBC/Voice 閘道的 [品牌] 和 [模型]。 請注意，您可以從已測試的裝置清單中，將裝置或 SIP [https://technet.Microsoft.com/UCOIP](https://technet.Microsoft.com/UCOIP)幹線連接至。  <br/> ||
|語音閘道2品牌與型號（如果您有超過2個閘道，請複製這個列）  <br/> |指定語音閘道的 [品牌] 和 [模型]。 請注意，您可以從已測試的裝置清單中，將[https://technet.Microsoft.com/UCOIP](https://technet.Microsoft.com/UCOIP)裝置連線。  <br/> ||
|語音閘道1名稱  <br/> |用來以 AD 網域產生電腦 FQDN。 如果要在轉送程式元件和語音閘道之間使用 TLS，則為必要。 如果您不打算使用 FQDN （例如，不需要 TLS，或語音閘道不支援使用 FQDN （僅限 IP）連線），請指定。  <br/> ||
|語音閘道2名稱（如果您有超過2個閘道，請複製這個列）  <br/> |用來以 AD 網域產生電腦 FQDN。 如果 TLS 將用於轉送程式元件與語音閘道之間，則為必要。 如果您不打算使用 FQDN （例如，不需要 TLS，或語音閘道不支援使用 FQDN （僅限 IP）連線），請指定。  <br/> ||
|語音閘道 1 IP 位址  <br/> |語音閘道的 IP 位址。  <br/> ||
|語音閘道 2 IP 位址（如果您有超過2個閘道，請複製這個列）  <br/> |語音閘道的 IP 位址。  <br/> ||
|語音閘道1埠 # （如果您有超過2個閘道，請複製這個列）  <br/> |語音閘道 SIP 幹線將接聽的埠，例如5060。  <br/> ||
|語音閘道2埠#  <br/> |語音閘道 SIP 幹線將接聽的埠，例如5060。  <br/> ||
|適用于 SIP 流量的語音閘道1通訊協定  <br/> |TCP 或 TLS。  <br/> ||
|適用于 SIP 流量的語音閘道2通訊協定（如果您有超過2個閘道，請複製這個列）  <br/> |TCP 或 TLS。  <br/> ||
|進出邊緣元件之流量的外部媒體埠範圍  <br/> |從 edge 的外部介面進出媒體流量的 TCP/UDP 埠範圍。 必須總是從 50 000 開始。 如需詳細資訊，請參閱「埠和通訊協定」。  <br/> |50000-59 999  <br/> |
|透過內部防火牆與匯調解元件進行通訊的媒體埠範圍  <br/> |轉送元件用來與用戶端和閘道通訊的 UDP 埠範圍（建議每個通話有4個埠）。  <br/> ||
|透過內部防火牆與商務用 Skype 用戶端通訊的媒體埠範圍  <br/> |出於規劃目的，無法變更。 在內部防火牆中必須開啟埠，才能在內部網路中的商務用 Skype 用戶端與流量分配元件進行通訊。  <br/> |50 000-50 019  <br/> |
|公用憑證密碼  <br/> |必須在腳本中提供。  <br/> ||
|安全模式系統管理員密碼  <br/> 僅限版本1.4。2  <br/> |內部抄送網域的安全模式系統管理員密碼。  <br/> ||
|雲端連接器網域系統管理員密碼  <br/> 僅限版本1.4。2  <br/> |雲端連接器網域系統管理員的密碼（與您的生產網域不同）。 [使用者名稱] 為 [管理員]。 您無法變更使用者名稱。  <br/> ||
|虛擬機器系統管理員密碼  <br/> 僅限版本1.4。2  <br/> |用於在部署期間設定管理網路。  <br/> [使用者名稱] 為 [管理員]。 您無法變更使用者名稱。  <br/> ||
|CABackupFile  <br/> 版本2.0 及更新版本  <br/> |在雲端連接器網站中部署多個裝置時，用來將憑證授權單位服務從 Active Directory 伺服器儲存到檔案。 請務必針對同一個雲端連接器網站中的所有裝置使用相同的密碼，以便將 CA 備份檔案匯入到新新增的裝置。  <br/> ||
|CCEService  <br/> 版本2.0 及更新版本  <br/> |用於雲端連接器管理服務;需要存取雲端連接器網站目錄。 請務必針對同一個雲端連接器網站中的所有裝置使用相同的密碼。  <br/> ||
|Office 365 租使用者系統管理員  <br/> | 雲端連接器使用該帳戶來更新及管理雲端連接器的租使用者設定： <br/>  版本2.0 及更新版本：具備商務用 Skype 系統管理員許可權的專用 Office 365 帳號憑證。 <br/>  2.0 的前幾個版本：具備全域租使用者管理員許可權的專用 Office 365 帳號憑證。 <br/> ||
|啟用參照支援  <br/> |這會定義在幹線設定上啟用或停用 SIP 對您 IP/PBX 所做的 SIP。 預設值為 True。 如果您的 IP/PBX 閘道支援參照支援，請將此屬性設為 True。 如果沒有，則需要將這個值變更為 False。 如果您不確定您的閘道是否支援參照，請參閱[合格的 IP-pbx 和閘道](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways)。   <br/> ||
|EnableFastFailoverTimer  <br/> 版本2.0 及更新版本  <br/> |在預設值為 "True" 的情況下，如果閘道不會在10秒內接聽撥出電話，它們將會路由至下一個可用的閘道;如果沒有其他 trunks，則會自動放棄通話。  <br/> 不過，在網路和閘道回應較慢的組織中，或當建立通話的程式需要10秒以上時，可能會導致不必要地刪除呼叫。  <br/> 在撥打電話給某些國家或地區時（例如 UAE 或阿富汗），通話建立程式可能需要10秒以上的時間才能完成。 如果您遇到類似的問題，您將需要將此值變更為 False。 請勿忘記在已連接的 SBC 或閘道上變更相對應的設定。  <br/> 值可以是 True 或 False。 預設值為 True。  <br/> ||
|ForwardCallHistory  <br/> 版本2.0 及更新版本  <br/> | 這個參數可用來開啟 SIP 標題，這些標頭是用來在同時撥打、來電轉接及來電轉接案例中，報告初始來電者。 將參數設定為 True 會開啟兩個 SIP 標頭： <br/>  歷程記錄-資訊 <br/>  參照者 <br/>  [歷程記錄-資訊] 標頭是用來重新導向 SIP 要求，以及「提供（s）標準機制來捕獲要求歷程記錄資訊，以便為網路和最終使用者提供多種服務」（[RFC 4244-區段 1.1](http://www.ietf.org/rfc/rfc4244.txt)）。 若是雲端連接器幹線介面，這會在 Simulring 和來電轉接案例中使用。  <br/>  值可以是 True 或 False。 預設值為 False。 <br/> ||
|轉寄 PAI  <br/> 版本2.0 及更新版本  <br/> |PAI 是 SIP 的私人延伸，可讓 SIP 伺服器斷言經過驗證的使用者身分識別。 對於 SIP 幹線提供者，PAI 可能會用於帳單用途，而記錄資訊和參照標頭則不存在。 在設定中啟用轉寄 P 斷言身分識別時，中繼伺服器會將 PAI 標頭與 SIP &amp;電話 URI 的從雲端連接器轉寄到 SIP 幹線。 中繼伺服器將會轉寄 PAI 標頭，且電話&amp; URI 的 E. 164 個數字只能在 SIP 主幹和雲端連接器上收到。 中繼伺服器也會轉寄任一方向接收到的任何隱私權標頭。 如果中繼伺服器傳送的 SIP 要求包含 [隱私權： id] 表單的隱私權標頭與 PAI 標頭，則斷言身分識別應該在網路信任網域外保密。  <br/> 值可以是 True 或 False。 預設值為 False。  <br/> ||

### <a name="certificate-requirements"></a>證書需求
<a name="BKMK_Certs"> </a>

每個 Edge 元件都需要來自公用憑證授權單位的憑證。 證書必須有可匯出的私密金鑰，才能在邊緣元件之間複製。 若要符合證書需求，您必須在下列選項之間決定，並為憑證提供 Subject 名稱（SN.EXE）與 Subject 備用名稱（SAN）。

 **如果您有單一 SIP 網域：**

- **選項1。** Subject 名稱必須包含您指派給 Edge 元件的 [池名稱]。 請注意，因為這個名稱是為線上商務用 Skype Edge 元件所保留，所以無法 sip.sipdomain.com 消費者名稱。 SAN 必須包含 sip.sipdomain.com 和存取邊緣池名稱：

  ```
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain.com,
  acessedgepoolnameforsite1.sipdomain.com
  ```

- **選項2。** 如果您想要在您部署的所有邊緣池伺服器上使用單一萬用字元憑證，您可以使用 sipdomain.com 的萬用字元 SAN 專案\*，而不是憑證中的邊緣池名稱。 Subject 名稱可以是您已部署的任何邊緣池的存取邊緣池名稱：

  ```
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain.com, SAN = *.sipdomain.com
  ```

> [!NOTE]
> 您不能建立 sip 的外部 DNS 專案。\<sipdomain\>，因為此名稱屬於 Office 365 部署。

> [!NOTE]
> 如果您想要針對貴組織中部署的所有邊緣池使用單一憑證，且無法使用在 option 2 中定義的萬用字元憑證，則您必須在憑證中的 SAN 名稱中包含所有部署的 Edge 池的 FQDN。

 **如果您有多個 SIP 網域：**

您必須為每個 SIP 網域加上 sip.sipdomain.com，以及每個網域的存取邊緣池名稱（可以是一個物理池，但名稱不同）。 以下是多個 sip 網域案例中的 SN 與 SAN 專案範例：

- **選項1。** Subject 名稱必須包含您為邊緣元件所指派的池子名稱。 請注意，因為這個名稱是為線上商務用 Skype Edge 元件所保留，所以無法 sip.sipdomain.com 消費者名稱。 SAN 必須包含 sip.sipdomain.com 和存取邊緣池名稱：

  ```
  SN = accessedgepoolnameforsite1.sipdomain1.com, SAN = sip.sipdomain1.com, sip.sipdomain2.com,
  acessedgepoolnameforsite1.sipdomain1.com
  ```

- <strong>選項2。</strong>如果您想要在您部署的所有邊緣池伺服器上使用單一萬用字元憑證，您可以使用 sipdomain.com 的萬用字元 SAN 專案\*，而不是憑證中的邊緣池名稱。 Subject 名稱可以是您已部署的任何邊緣池的存取邊緣池名稱：

  ```
  SN = accessedgepoolnameforsite1.sipdomain.com, SAN = sip.sipdomain1.com, sip.sipdomain2.com,
  SAN = *.sipdomain1.com
  ```

> [!NOTE]
> 您不能建立 sip 的外部 DNS 專案。\<sipdomain\>，因為此名稱屬於 Office 365 部署。

針對部署的目的，您可以使用下表：

|**件**|**描述**|**筆記**|
|:-----|:-----|:-----|
|您將在部署中使用哪個選項？  <br/> |選項1或2  <br/> ||
|SN.EXE  <br/> |為您的憑證提供 SN  <br/> ||
|上海  <br/> |為您的憑證提供 SAN  <br/> ||

如果您是在閘道與中繼伺服器之間使用 TLS，您將需要取得指派給閘道之憑證的根憑證或完整憑證連結。

## <a name="dial-plan-considerations"></a>撥號方案考慮
<a name="BKMK_DailPlan"> </a>

雲端連接器需要使用線上撥號方案。 如需如何設定線上撥號方案的詳細資訊，請參閱[什麼是撥號方案？](/microsoftteams/what-are-dial-plans) 
  
## <a name="high-availability-considerations"></a>高可用性考慮
<a name="BKMK_HA"> </a>

當您部署雲端連接器版本以取得高可用性時，請至少部署兩個裝置，以做為其他作用中的備份。 每個裝置都由四個元件組成： Edge、採集轉送、中央管理商店（CMS）及網網域控制站。

一般來說，如果裝置中的某個元件出現故障，雲端連接器版本可以繼續處理通話，但您必須考慮下列事項：

- **轉送、CMS 及網網域控制站元件考慮**

    假設某個裝置中的 CMS 或網網域控制站元件發生故障。 裝置仍可處理入站和出站通話，但如果您在無法達到網網域控制站或 CMS 元件時重新開機轉送元件，則無法使用轉送作業。 當網網域控制站關閉時，同樣適用于重新開機 CMS 元件。

    **建議：** 重新開機元件之前，請先檢查裝置中其他元件的可用性。

- **邊緣元件考慮**

    如果某個裝置中的邊緣元件無法使用，則入站和出站通話的行為會與下列專案有所不同：

  - [撥**出通話**]-從網際網路到 PSTN 網路的呼叫。

    雲端中的呼叫散佈機制會識別出一個邊緣元件已關閉，並將所有呼叫路由到另一個裝置，因此傳出通話成功。

  - [撥**入通話**]-從 PSTN 網路撥打電話給在本機網路或網際網路中的使用者。

     如果收件者的裝置元件無法正常運作，由於轉送元件無法將呼叫重新導向到其他裝置中的邊緣元件，所以此裝置的撥入呼叫將無法成功。

    **建議：** 讓監視系統在適當的地方。 在您找出邊緣元件的故障之後，請關閉裝置中無法使用 Edge 元件的所有元件。

## <a name="cloud-connector-media-flow"></a>雲端連接器媒體流程
<a name="BKMK_MediaFlow"> </a>

下列圖表概述透過雲端連接器版本進行的傳出和撥出通話流程。 這是瞭解如何建立連線的實用資訊。

在第一個圖表中，內部使用者會按照下列步驟進行撥出通話：

1. Dave，使用者位於線上，但現在在內部網路中，會撥打電話給外部 PSTN 使用者。

2. SIP 流量路由到商務用 Skype Online。

3. 商務用 Skype Online 會針對數位執行反向編號查閱。 [反向數位查閱] 失敗，因為這個數位不屬於商務用 Skype 組織中的任何人。

4. 通話會路由至 Edge 元件（首先透過線上邊緣傳送 SIP 和媒體流程;媒體會透過內部防火牆移至轉送程式元件）。

5. 如果路由存在，則邊緣元件會將流量中繼到周邊網路中的轉送轉送元件。

6. 採集轉送元件會將流量傳送到 PSTN 閘道。

![雲端連接器的輸出媒體流程](../../media/c495a2bb-305c-46ef-b16d-b8f9f2b937a8.png)

在下一個圖表中，內部使用者會收到如下所示的撥入通話：

1. PSTN 閘道會針對目前線上的使用者 Dave 接聽電話，但現在是在內部網路中。

2. SIP 流量會路由到轉送所組成的元件。

3. 轉送程式元件會將 SIP 流量傳送到 Edge 元件，然後移至商務用 Skype Online。

4. 商務用 Skype Online 會對數位進行反向編號查閱，併發現這是使用者 Dave。

5. SIP 信號會移至所有 Dave 的目前狀態點。

6. 媒體流量將在閘道與轉送元件之間，以及在流量分配元件與結束點之間建立。

![雲端連接器的入站媒體流程](../../media/ba5da6f6-e357-43c6-9e8f-4bfdde97c176.png)

## <a name="monitoring-and-troubleshooting"></a>監控和疑難排解
<a name="BKMK_Monitor"> </a>

每個雲端連接器裝置會自動安裝監控與疑難排解機制。 該機制會偵測到下列事件：

- 一或多個雲端連接器裝置的虛擬機器未連線至內部或網際網路虛擬交換器。

- 一或多個雲端連接器裝置的虛擬機器處於 [已儲存] 或 [已停止] 狀態。

- 未執行的服務。

  如果偵測到下列其中一個事件，整個雲端連接器裝置就會排出並標示為 [離線]，以免試圖建立無法正常使用的裝置的呼叫。 雲端連接器自動復原功能將會隨後還原服務，並將裝置標示為線上。 如果自動復原由於某種原因而失敗，請參閱[疑難排解您的雲端連接器部署](troubleshoot-your-cloud-connector-deployment.md)。

  - 在中央管理儲存虛擬機器上：

     - 商務用 Skype 主版複製器代理程式

     - 商務用 Skype 複本複製器代理程式

  - 在中繼伺服器虛擬機器上：

     - 商務用 Skype 複本複製器代理程式

     - 商務用 Skype Server 轉送

  - 在 Edge 伺服器虛擬電腦上

     - 商務用 Skype 複本複製器代理程式

     -  商務用 Skype Server 存取邊緣

     - 商務用 Skype Server 音訊/視頻邊緣

     - 商務用 Skype Server 音訊/視頻驗證

     - 商務用 Skype Server Web 會議邊緣

- 「CS RTCSRV」的 Windows 防火牆的入站規則在 Edge 上是停用的 [CS RTCMEDSRV]。

雲端連接器2.1 及更新版本支援使用 Operations Management Suite （OMS）來監視雲端連接器。 如需詳細資訊，請參閱[使用 Operations Management Suite （OMS）監視雲端連接器](monitor-cloud-connector-using-operations-management-suite-oms.md)

## <a name="for-more-information"></a>如需詳細資訊
<a name="BKMK_MoreInfo"> </a>

如需詳細資訊，請參閱下列內容：

- [Microsoft 電話語音解決方案](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/msft-telephony-solutions)

- [設定及管理商務用 Skype 雲端連接器版本](configure-skype-for-business-cloud-connector-edition.md)

- [規劃 Cloud Connector Edition 中的媒體旁路](plan-for-media-bypass-in-cloud-connector-edition.md)

- [在雲端連接器版本中部署媒體旁路](deploy-media-bypass-in-cloud-connector.md)


