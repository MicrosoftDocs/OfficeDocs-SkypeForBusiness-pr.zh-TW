---
title: Lync Server 2013：SIP 主幹上的通話許可控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call admission control on a SIP trunk
ms:assetid: 7eada098-3d47-4be2-839f-8f87d582efe8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398632(v=OCS.15)
ms:contentKeyID: 48184623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 36734aa67e350b6c6f5ea5e9da57ce47f57e3d46
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977017"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-on-a-sip-trunk-in-lync-server-2013"></a>Lync Server 2013 中的 SIP 主幹上的通話許可控制

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-22_

若要在 SIP 主幹上部署呼叫許可控制（CAC），您需要建立網路網站來代表網際網路電話服務提供者（ITSP）。 若要在 SIP 主幹上套用頻寬原則值，您可以在企業中的網路網站和您建立用以代表 ITSP 的網路網站之間建立站間原則。

下圖顯示 SIP 主幹上的 CAC 部署範例。

**SIP 幹線上的 CAC 配置**

![呼叫許可控制 Sip 中繼圖表](images/Gg398632.276c0d8f-1dd5-4883-8499-c202399ddbe9(OCS.15).jpg "通話許可控制 sip 中繼圖表")

若要在 SIP 主幹上設定 CAC，您必須在 CAC 部署期間執行下列工作：

1.  建立代表 ITSP 的網路網站。 將網路網站與合適的網路區域建立關聯，並為此網路網站的音訊和影片分配零頻寬。 如需詳細資訊，請參閱在部署檔中的[Lync Server 2013 中設定 CAC 的網路網站](lync-server-2013-configure-network-sites-for-cac.md)。
    
    <div>
    

    > [!NOTE]  
    > 針對 ITSP，此網路網站設定無法正常運作。 在步驟2中實際會套用頻寬原則值。

    
    </div>

2.  使用您在步驟1中建立的網站相關參數值，為 SIP 幹線建立站間連結。 例如，在企業中使用網路網站的名稱做為 NetworkSiteID1 參數的值，並使用 ITSP network 網站作為 NetworkSiteID2 參數的值。 如需詳細資訊，請參閱部署檔中的[Lync Server 2013 中的建立網路站間原則](lync-server-2013-create-network-intersite-policies.md)。 另請參閱適用于新版 CsNetworkInterSitePolicy Cmdlet 的 Lync Server 管理命令介面檔。

3.  從您的 ITSP 取得會話邊界控制器（SCB）媒體終止點的 IP 位址。 將具有子網路遮罩32的 IP 位址新增至代表 ITSP 的網路網站。 如需詳細資訊，請參閱[在 Lync Server 2013 中將子網與網路網站建立關聯](lync-server-2013-associate-a-subnet-with-a-network-site.md)。

</div>

<span> </span>

</div>

</div>

</div>

