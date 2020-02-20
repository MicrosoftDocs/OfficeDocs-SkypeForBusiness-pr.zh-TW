---
title: Lync Server 2013： 部署 Enterprise Voice
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Enterprise Voice
ms:assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412876(v=OCS.15)
ms:contentKeyID: 48185207
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b56065b0e3b7e7ef25c81f20140e8869dbe5376
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151333"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-enterprise-voice-in-lync-server-2013"></a>部署 Lync Server 2013 中的 Enterprise Voice

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-03_

Lync Server 2013、 Enterprise Voice 為 Lync Server 2013 基礎結構的一部分。

部署 Enterprise Voice 需要您：

<div id="sectionSection0" class="section">

1.  請先檢閱[Planning for Lync Server 2013 中的企業語音](lync-server-2013-planning-for-enterprise-voice.md)] 區段中的規劃文件。

2.  完成功能與元件的計劃，使用此工作負載來部署。

3.  執行規劃工具設計拓撲，以反映您的部署決策。

4.  中所述[定義和設定 Lync Server 2013 中的拓撲](lync-server-2013-defining-and-configuring-the-topology.md)中部署文件，請在拓撲產生器] 中開啟拓撲設計。
    
    <div>
    

    > [!NOTE]  
    > 安裝拓撲產生器是內部集區的部署程序的一部分。 如需詳細資訊，請參閱部署文件中的<A href="lync-server-2013-install-lync-server-administrative-tools.md">安裝 Lync Server 2013 系統管理工具</A>。

    
    </div>

此外，您必須已部署 Lync Server，Enterprise Edition，中央站台和對應至您選擇要部署的參考拓撲的分支網站。 您無法部署企業語音元件，直到您已定義、 發行及安裝檔案來至少一個內部集區，您必須使用拓撲產生器來定義和發佈的內部集區。

</div>

<div id="sectionSection1" class="section">

<div class="subSection">

若要檢視部署企業語音的伺服器角色的位置 （和其關係到另一個和其他 Lync Server 2013 伺服器角色） 的範例與參考拓撲，請參閱規劃文件中的[Lync Server 2013 中的參考拓撲](lync-server-2013-reference-topologies.md)。

若要檢視的參考拓撲顯示及說明範例通話許可控制部署，包括網路地區、 網站及網路子網路，請參閱[範例： 收集您的 Lync Server 2013 中的通話許可控制需求](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)中規劃文件。

</div>

</div>

<div id="sectionSection2" class="section">

<div>


> [!IMPORTANT]  
> 若要部署 Enterprise Voice 在中央網站，請繼續閱讀本章節中的主題。 若要部署 Enterprise Voice 在分支網站，跳至<A href="lync-server-2013-deploying-branch-sites.md">Lync Server 2013 中部署分支網站</A>部署文件中。



</div>

本節包含部署程的序，在每部前端伺服器或 Standard Edition 伺服器上，此中繼伺服器已組合的建議，以及具有獨立的中繼伺服器集區的部署。

如果您使用拓撲產生器中定義並發行拓撲，配置中繼伺服器上每個前端伺服器或 Standard Edition 伺服器，因為部署精靈已自動安裝的檔案，您可以略過下列內容當您安裝適用於您的前端伺服器集區或 Standard Edition server 檔案的中繼伺服器：

  - [在 Lync Server 2013 中設定主幹](lync-server-2013-configuring-trunks.md)

如果您使用拓撲產生器來定義和發佈中繼伺服器的獨立集區中，您可以使用下列內容：

  - 確認您的拓撲符合軟體和環境先決條件，[針對 Lync Server 2013 Enterprise Voice 必要條件](lync-server-2013-enterprise-voice-prerequisites.md)中所述。

</div>

<div>

## <a name="in-this-section"></a>本章節內容

  - <span></span>  
    [Lync Server 2013 Enterprise Voice 先決條件](lync-server-2013-enterprise-voice-prerequisites.md)

  - <span></span>  
    [部署中繼伺服器和 Lync Server 2013 中定義 peers](lync-server-2013-deploying-mediation-servers-and-defining-peers.md)

  - <span></span>  
    [在 Lync Server 2013 中設定主幹](lync-server-2013-configuring-trunks.md)

  - <span></span>  
    [Lync Server 2013 中設定撥號對應表](lync-server-2013-configuring-dial-plans.md)

  - <span></span>  
    [在 Lync Server 2013 中設定語音原則、 PSTN 使用方式記錄和語音路由](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)

  - <span></span>  
    [匯出及匯入 Lync Server 2013 中的語音路由設定](lync-server-2013-exporting-and-importing-voice-routing-configuration.md)

  - <span></span>  
    [測試 Lync Server 2013 中的語音路由](lync-server-2013-test-voice-routing.md)

  - <span></span>  
    [暫止的變更語音路由設定 Lync Server 2013 中發佈](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

  - <span></span>  
    [部署內部部署 Exchange UM 以提供 Lync Server 2013 語音信箱](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)

  - <span></span>  
    [提供 Lync Server 2013 使用者語音信箱上裝載的 Exchange UM](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)

  - <span></span>  
    [設定與 Exchange Online 內部部署 Lync Server 2013 整合](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md)

  - <span></span>  
    [部署 Lync Server 2013 中的進階的 Enterprise Voice 功能](lync-server-2013-deploying-advanced-enterprise-voice-features.md)
    
      - [關於網路地區、 網站及 Lync Server 2013 中的子網路](lync-server-2013-about-network-regions-sites-and-subnets.md)
    
      - [建立或修改 Lync Server 2013 中的網路區域](lync-server-2013-create-or-modify-a-network-region.md)
    
      - [建立或修改 Lync Server 2013 中的網路網站](lync-server-2013-create-or-modify-a-network-site.md)
    
      - [關聯子網路與 Lync Server 2013 中的網路網站](lync-server-2013-associate-a-subnet-with-a-network-site.md)
    
      - [在 Lync Server 2013 中設定通話許可控制](lync-server-2013-configure-call-admission-control.md)
    
      - [在 Lync Server 2013 中設定增強型的 9-1-1](lync-server-2013-configure-enhanced-9-1-1.md)
    
      - [在 Lync Server 2013 中設定媒體旁路](lync-server-2013-configure-media-bypass.md)

  - <span></span>  
    [啟用使用者的 Lync Server 2013 中的 Enterprise Voice](lync-server-2013-enable-users-for-enterprise-voice.md)

</div>

<div>

## <a name="see-also"></a>另請參閱


[部署 Lync Server 2013 中的分支網站](lync-server-2013-deploying-branch-sites.md)  
[在 Lync Server 2013 中設定電話撥入式會議](lync-server-2013-configuring-dial-in-conferencing.md)  
[在 Lync Server 2013 中設定通話駐留](lync-server-2013-configuring-call-park.md)  
[在 Lync Server 2013 中設定未指派號碼的宣告](lync-server-2013-configuring-announcements-for-unassigned-numbers.md)  
[部署 Lync Server 2013 中監視](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

