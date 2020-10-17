---
title: Lync Server 2013 支援的拓撲
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported topologies
ms:assetid: 3475d430-0394-491b-a09b-ba85bd62be70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425833(v=OCS.15)
ms:contentKeyID: 48183832
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4754881d2ed3205c4f06d5468001c6e45880278c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523960"
---
# <a name="supported-topologies-in-lync-server-2013"></a>Lync Server 2013 中支援的拓撲

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-01-14_

Lync Server 2013 支援在組織內部部署網站，並整合內部部署與 Lync Online 部署（稱為「混合部署」）。 在混合部署中，一些使用者會位於內部部署，而一些使用者會位於線上。

若為內部部署，Lync Server 2013 可支援部署一或多個網站，以符合高可用性和位置需求。 您可以建構這些站台及其元件，以達到組織在存取與恢復能力方面的需求。

Lync Server 2013 內部部署是由下列專案所組成：

  - 部署中至少要有一個中央站台 (也稱為資料中心)。每個中央站台都至少要有一個 Enterprise Edition 前端集區或一部 Standard Edition Server。這些項目包含：
    
      - Enterprise Edition 前端集區，由一或多部前端伺服器 (通常至少兩部前端伺服器，以維持延展性) 與一部個別的後端伺服器所組成。 前端集區最多可包含十二部前端伺服器。 多部前端伺服器間必須使用負載平衡。 針對 SIP 流量，建議您使用 DNS 負載平衡，但也支援硬體負載平衡。 如果您對 SIP 流量使用 DNS 負載平衡，您仍需要適用於 HTTP 流量的硬體負載平衡器。 建議資料庫的高可用性的 SQL Server 鏡像。 後端資料庫必須要有個別的執行個體，但您可以將封存資料庫、監控資料庫、常設聊天室資料庫，以及常設聊天室規範資料庫與其組合。 Lync Server 2013 支援對部署中的檔案共用使用共用叢集。 如需資料庫儲存需求的詳細資訊，請參閱 [Lync Server 2013 中的資料庫軟體支援](lync-server-2013-database-software-support.md)。 如需檔案儲存需求的詳細資訊，請參閱 [Lync Server 2013 中的檔案儲存支援](lync-server-2013-file-storage-support.md)。
        
        <div>
        

        > [!IMPORTANT]  
        > 如果您組合 Lync Server 資料庫，強烈建議評估可能影響可用性及效能的所有因素。 若要確認容錯移轉功能，建議您測試所有容錯移轉狀況。

        
        </div>
    
      - Standard Edition Server，其中包含組合的 SQL Server Express 資料庫。

  - 部署中也可以有一或多個與中央網站相關聯的分支網站。

本節說明 Lync Server 2013 部署的網站和元件。 如需 Lync Server 2013 網站、拓撲及元件規劃的詳細資訊，請參閱規劃檔中的 lync server 2013 和[Lync server 2013](lync-server-2013-reference-topologies.md)中[規劃 lync Server 及參考拓撲之前，必須先知道的拓撲基本知識](lync-server-2013-topology-basics-you-must-know-before-planning.md)。 如需與舊版元件整合相關的詳細資訊，請參閱 [Lync Server 2013 中支援的遷移路徑和共存案例](lync-server-2013-supported-migration-paths-and-coexistence-scenarios.md)。

<div>


> [!NOTE]  
> 「前端」、「Edge」、「中繼」和「Director」伺服器角色都不支援延伸集區。



</div>

<div>

## <a name="central-site-topologies-and-components-on-premises"></a>中央站台的拓撲與元件 (內部部署)

雖然中央站台拓撲必須包含一個前端集區或一部 Standard Edition Server，但各個中央站台也可包含下列項目：

  - 多個前端集區，可位於相同或不同的網域。但是，前端集區中的所有前端伺服器與該集區的後端伺服器必須位於相同網域。

  - 多部 Standard Edition Server。

  - Office Web Apps Server，可與 Lync Server 2013 中的 Office Web 應用程式搭配使用，以處理 Microsoft PowerPoint 簡報的共用及呈現。

  - Edge Server 或 Edge 集區在周邊網路中，如果您想要部署支援同盟協力廠商、公用 IM 連線、可延伸的訊息和顯示狀態通訊協定 (XMPP) 閘道、遠端使用者存取、匿名使用者加入會議或 Exchange 整合通訊 (UM) 。 Edge Server 不可與任何其他伺服器角色組合。 建議在情況允許時使用 DNS 負載平衡，但也支援硬體負載平衡。 內部 Edge 介面和外部 Edge 介面必須使用相同類型的負載平衡。 您不能在一個 Edge 介面上使用 DNS 負載平衡，而在另一個 Edge 介面上使用硬體負載平衡。 如需負載平衡需求和支援的詳細資訊，請參閱部署檔中的規劃檔和[部署外部使用者2013存取](lync-server-2013-deploying-external-user-access.md)中的 [在 lync server [2013 中規劃外部使用者存取](lync-server-2013-planning-for-external-user-access.md)]。

  - 轉送伺服器或集區，如果您想要在中央網站的前端集區中支援 Enterprise Voice 或電話撥入式會議。 根據您部署企業語音支援的方式，您可以在 (預設) 或部署獨立轉送伺服器或集區的前端集區中組合轉送伺服器。 當適當) 從轉送伺服器集區的閘道對等發佈流量（包括 PSTN 閘道、IP-PBX 或 SIP 主幹會話邊界 (SBC) ）時，您可以使用 DNS、硬體或應用程式負載平衡 (。如需規劃適當轉送伺服器拓撲的詳細資訊，請參閱規劃檔中的 [Lync server 2013 中的轉送伺服器部署指導方針](lync-server-2013-deployment-guidelines-for-mediation-server.md) 。

  - Persistent Chat Server，如果您想要讓使用者能夠參與多方，以主題為基礎的交談會隨著時間而保留。 若要提供更多的容量及增強的可靠性，您的拓撲可包含多部執行 Persistent Chat Server 的電腦。 您無法組合 Persistent Chat Server 與企業版集區中的其他伺服器角色。 不過，您可以在 Standard Edition server 上組合 Persistent Chat Server。 常設聊天室需要一個資料庫，而且，如果您實作常設聊天室規範，則需要常設聊天室規範資料庫，但是資料庫可與封存資料庫或監控資料庫組合，或者在 Enterprise Edition 前端集區的後端伺服器上組合。 如需規劃適當之持久聊天伺服器拓撲的詳細資訊，請參閱規劃檔中的在 [Lync server 2013 中規劃 Persistent Chat Server](lync-server-2013-planning-for-persistent-chat-server.md) 。

  - 監控 (如果您要在部署中支援音訊/視訊經驗品質 (QoE) 的資料收集以及企業語音與 A/V 會議的詳細通話記錄 (CDR))。 您也可以選擇安裝 Microsoft System Center Operations Manager (過去的 Microsoft Operations Manager) ，它會使用監控 CDR 和 QoE 資料來產生接近即時的警報，以顯示通話可靠性和媒體質量的健康情況。 在部署時，監控可與前端伺服器或 Standard Edition Server 組合。 監控必須要有資料庫，但此資料庫可與封存伺服器、常設聊天室資料庫、常設聊天室規範資料庫或 Enterprise Edition 前端集區的後端伺服器組合。

  - 封存 (如果您基於規範而要在部署中封存 IM 通訊與會議內容)。 在部署時，封存可與前端伺服器或 Standard Edition Server 組合。 封存儲存需要部署封存資料庫或與 Exchange 2013 儲存體整合。 如果您同時使用這兩種模式，又稱為 *混合模式*，exchange 2013 儲存區是用來儲存位於 Exchange 2013 上之使用者的封存資料，而封存資料庫是用來封存部署中所有其他使用者的資料。 如果您需要封存資料庫，該資料庫可以在監控資料庫、常設聊天室資料庫、常設聊天室規範資料庫或前端集區的後端伺服器上組合。 如需規劃適當封存拓撲的詳細資訊，請參閱規劃檔中的 [規劃在 Lync Server 2013 中的](lync-server-2013-planning-for-archiving.md) 封存。

  - Director 或 Director 集區，如果您想要對使用者的主集區（可以是 Enterprise Edition 前端集區或 Standard Edition Server）進行恢復與重新導向，以進行 Lync Server 2013 使用者要求的恢復與重新導向。 建議您在每個支援外部使用者存取的中央站台以及每個部署一或多個前端集區的中央站台上，部署 Director 或 Director 集區。 每個 Director 集區最多可包含十個 Director。 Director 不可與任何其他伺服器角色組合。 如需規劃適當 Director 拓撲的詳細資訊，請參閱規劃檔中的 [Lync Server 2013 中的 Director 案例](lync-server-2013-scenarios-for-the-director.md) 。

  - 反向 proxy （不是 Lync Server 2013 元件），但是如果您想要支援同盟使用者的 web 內容共用或支援行動性流量，則需要。 您無法使用任何 Lync Server 2013 伺服器角色組合反向 proxy 伺服器，但您可以在組織中對其他應用程式使用的現有反向 proxy 伺服器上設定支援，以執行 Lync Server 2013 部署的反向 proxy 支援。 如需反向 proxy 伺服器的詳細資訊，請參閱部署檔中的 [設定 Lync Server 2013 的反向 proxy 伺服器](lync-server-2013-setting-up-reverse-proxy-servers.md) 。

<div>


> [!NOTE]  
> 在 Lync Server 2013 中，A/V 的會議、監控和封存都是在前端伺服器上執行，而且不再是個別的伺服器角色。



</div>

您在中央網站上部署的所有前端集區與 Standard Edition Server，將會共用您為中央網站所部署的下列各項：

  - Director 或 Director 集區

  - 獨立式中繼伺服器或集區

  - Office Web Apps Server

  - Edge Server 或 Edge 集區

  - 常設聊天室伺服器或集區

  - 監視

  - 封存

<div>


> [!NOTE]  
> 如果您想要支援 Exchange 2013 整合通訊的整合，但它不是 Lync Server 2013 網站的元件，則可以在您的 Lync Server 2013 部署中實施 Exchange UM 伺服器。



</div>

多個中央網站也可共用您在某個中央網站上部署的下列任何項目：

  - 獨立式中繼伺服器或集區

  - Edge Server 或 Edge 集區

  - 常設聊天室伺服器或集區

  - 封存

  - 監視

<div>


> [!NOTE]  
> Exchange UM 伺服器可與您的 Lync Server 2013 部署搭配執行，並由多部中央網站共用，但它不是 Lync Server 2013 網站的元件。



</div>

如需 Lync Server 2013 伺服器角色及功能的詳細資訊，請參閱規劃檔中的 [Lync server 2013 中的伺服器角色](lync-server-2013-server-roles.md) 。

如需 Lync Server 2013 Server 組合支援的摘要，請參閱 [Lync server 2013 中的支援伺服器組合](lync-server-2013-supported-server-collocation.md)。

除了本節先前所涵蓋的伺服器角色和功能之外，Lync Server 2013 還有其他元件和選項，其中包括下列部分或所有專案：

  - 防火牆

  - PSTN 閘道 (如果部署企業語音)

  - Exchange UM 伺服器

  - DNS 負載平衡

  - 硬體負載平衡器

  - SQL Server 資料庫

  - 檔案共用

如需所有 Lync Server 2013 功能、元件及選項的詳細資訊，請參閱規劃檔。

</div>

<div>

## <a name="branch-site-topologies-and-components-on-premises"></a>分支站台的拓撲與元件 (內部部署)

分支站台會與中央站台相關聯，而且分支站台中的每個 Survivable Branch Appliance 都會與相關聯之中央站台上的一個 Enterprise Edition 前端集區或一部 Standard Edition Server 相關聯。分支站台大部分的功能皆依存於中央站台，因此分支站台上的元件僅包含下列項目：

  - Survivable 分支裝置，將公用交換電話網路 (PSTN) 閘道與某些 Lync Server 功能結合在一起。 您可以使用 Survivable Branch 裝置上的註冊機構實例來組合轉送伺服器，也可以部署一部獨立的轉送伺服器或轉送伺服器集區。

  - Survivable 分支伺服器，這是執行 Windows Server 且已安裝 Lync Server 2013 註冊機構和轉送伺服器軟體的伺服器。

  - 獨立式 PSTN 閘道 (不是 Survivable Branch Appliance 的一部分) 與獨立式中繼伺服器。

Survivable 分支伺服器的需求與任何 Lync Server 2013 伺服器角色的需求相同。

</div>

</div>

<span> </span>

</div>

</div>

</div>

