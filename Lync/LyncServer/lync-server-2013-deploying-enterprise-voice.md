---
title: Lync Server 2013：部署企業語音
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
ms.openlocfilehash: 4b2784c5cb04994004503010426ebc98763c0250
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531146"
---
# <a name="deploying-enterprise-voice-in-lync-server-2013"></a>在 Lync Server 2013 中部署企業語音

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-03_

Lync Server 2013，Enterprise Voice 是 Lync Server 2013 基礎結構的一部分。

部署 Enterprise Voice 時，需要您：

<div id="sectionSection0" class="section">

1.  請參閱規劃檔中的《 [Lync Server 2013 規劃中的企業語音規劃](lync-server-2013-planning-for-enterprise-voice.md) 」一節。

2.  完成與此工作負載一起部署的功能與元件的計畫。

3.  執行規劃工具來設計拓撲，以反映您的部署決策。

4.  開啟拓撲產生器中的拓撲設計，如在部署檔中的 [定義及設定 Lync Server 2013 中的拓撲](lync-server-2013-defining-and-configuring-the-topology.md) 所述。
    
    <div>
    

    > [!NOTE]  
    > 安裝拓撲產生器是內部集區之部署程式的一部分。 如需詳細資訊，請參閱部署檔中的 <A href="lync-server-2013-install-lync-server-administrative-tools.md">安裝 Lync Server 2013 系統管理工具</A> 。

    
    </div>

此外，您還必須已在中央網站和分支網站上部署 Lync Server Enterprise Edition，並對應至您選擇要部署的參考拓撲。 您必須先定義、發佈和安裝至少一個內部集區的檔案，然後再使用拓撲產生器來定義及發行內部集區，才能部署 Enterprise Voice 元件。

</div>

<div id="sectionSection1" class="section">

<div class="subSection">

若要查看參考拓撲，其可部署 Enterprise Voice server role 的範例，以及其與其他 (和其他 Lync Server 2013 伺服器) 角色的關聯性，請參閱規劃檔中的 [Lync server 2013 中的參考拓撲](lync-server-2013-reference-topologies.md) 。

若要查看說明及說明範例通話許可控制部署（包括網路地區、網路網站及子網）的參考拓撲，請參閱規劃檔中的 [範例：在 Lync Server 2013 中收集通話許可控制需求](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) 。

</div>

</div>

<div id="sectionSection2" class="section">

<div>


> [!IMPORTANT]  
> 若要在中央網站部署企業語音，請繼續閱讀本節中的主題。 若要在分支網站部署企業語音，請跳過部署檔中的 <A href="lync-server-2013-deploying-branch-sites.md">Lync Server 2013 中的部署分支網站</A> 。



</div>

本節包含在每一部前端伺服器或 Standard Edition server 上組合轉送伺服器的部署程式，如建議，也適用于具備獨立轉送伺服器集區的部署。

如果您使用拓撲產生器來定義及發行每一部前端伺服器或 Standard Edition server 上的轉送伺服器的拓撲，您可以略過下列內容，因為當您為前端伺服器集區或 Standard Edition server 安裝檔時，部署嚮導已自動安裝轉送伺服器的檔案：

  - [在 Lync Server 2013 中設定主幹](lync-server-2013-configuring-trunks.md)

如果您使用拓撲產生器來定義及發行獨立集區中的轉送伺服器，您可以使用下列內容：

  - 請確認您的拓撲符合軟體和環境必要條件（如 [Lync Server 2013 的 Enterprise Voice 必要條件](lync-server-2013-enterprise-voice-prerequisites.md)所述）。

</div>

<div>

## <a name="in-this-section"></a>本章節內容

  - <span></span>  
    [Lync Server 2013 的 Enterprise Voice 必要條件](lync-server-2013-enterprise-voice-prerequisites.md)

  - <span></span>  
    [在 Lync Server 2013 中部署轉送伺服器及定義對等專案](lync-server-2013-deploying-mediation-servers-and-defining-peers.md)

  - <span></span>  
    [在 Lync Server 2013 中設定主幹](lync-server-2013-configuring-trunks.md)

  - <span></span>  
    [在 Lync Server 2013 中設定撥號對應表](lync-server-2013-configuring-dial-plans.md)

  - <span></span>  
    [在 Lync Server 2013 中設定語音原則、PSTN 使用方式記錄和語音路由](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)

  - <span></span>  
    [在 Lync Server 2013 中匯出及匯入語音路由設定](lync-server-2013-exporting-and-importing-voice-routing-configuration.md)

  - <span></span>  
    [在 Lync Server 2013 中測試語音路由](lync-server-2013-test-voice-routing.md)

  - <span></span>  
    [在 Lync Server 2013 中將擱置的變更發佈至語音路由設定](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

  - <span></span>  
    [部署內部部署 Exchange UM 以提供 Lync Server 2013 語音信箱](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)

  - <span></span>  
    [在主控 Exchange UM 上提供 Lync Server 2013 使用者語音信箱](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)

  - <span></span>  
    [設定內部部署 Lync Server 2013 與 Exchange Online 整合](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md)

  - <span></span>  
    [在 Lync Server 2013 中部署高級 Enterprise Voice 功能](lync-server-2013-deploying-advanced-enterprise-voice-features.md)
    
      - [關於 Lync Server 2013 中的網路地區、網站和子網](lync-server-2013-about-network-regions-sites-and-subnets.md)
    
      - [在 Lync Server 2013 中建立或修改網路地區](lync-server-2013-create-or-modify-a-network-region.md)
    
      - [在 Lync Server 2013 中建立或修改網路網站](lync-server-2013-create-or-modify-a-network-site.md)
    
      - [在 Lync Server 2013 中建立子網與網路網站的關聯](lync-server-2013-associate-a-subnet-with-a-network-site.md)
    
      - [在 Lync Server 2013 中設定通話許可控制](lync-server-2013-configure-call-admission-control.md)
    
      - [在 Lync Server 2013 中設定增強型9-1-1](lync-server-2013-configure-enhanced-9-1-1.md)
    
      - [在 Lync Server 2013 中設定媒體旁路](lync-server-2013-configure-media-bypass.md)

  - <span></span>  
    [在 Lync Server 2013 中啟用使用者的 Enterprise Voice](lync-server-2013-enable-users-for-enterprise-voice.md)

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中部署分支網站](lync-server-2013-deploying-branch-sites.md)  
[在 Lync Server 2013 中設定電話撥入式會議](lync-server-2013-configuring-dial-in-conferencing.md)  
[在 Lync Server 2013 中設定通話駐留](lync-server-2013-configuring-call-park.md)  
[在 Lync Server 2013 中設定未指派號碼的宣告](lync-server-2013-configuring-announcements-for-unassigned-numbers.md)  
[在 Lync Server 2013 中部署監控](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

