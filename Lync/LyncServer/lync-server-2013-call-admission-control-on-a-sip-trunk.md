---
title: Lync Server 2013： SIP 主幹上的通話許可控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call admission control on a SIP trunk
ms:assetid: 7eada098-3d47-4be2-839f-8f87d582efe8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398632(v=OCS.15)
ms:contentKeyID: 48184623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bb2f12b395215c0b09fa650508cf93f1aec58d7f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512960"
---
# <a name="call-admission-control-on-a-sip-trunk-in-lync-server-2013"></a>Lync Server 2013 的 SIP 主幹上的通話許可控制

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-22_

若要在 SIP 主幹上部署通話許可控制 (CAC)，您必須建立代表網際網路電話語音服務提供者 (ITSP) 的網路網站。若要在 SIP 主幹上套用頻寬原則值，您可以在企業中的網路網站與您建立以代表 ITSP 的網路網站之間，建立網站間原則。

下圖顯示在 SIP 主幹上部署 CAC 的範例。

**SIP 主幹上的 CAC 組態**

![通話許可控制 SIP 主幹圖表](images/Gg398632.276c0d8f-1dd5-4883-8499-c202399ddbe9(OCS.15).jpg "通話許可控制 SIP 主幹圖表")

若要在 SIP 主幹上設定 CAC，您必須在 CAC 部署期間執行下列工作：

1.  建立代表 ITSP 的網路網站。 讓此網路網站與適當的網路地區相關聯，並為此網路網站的音訊與視訊功能配置零的頻寬。 如需詳細資訊，請參閱部署檔中的 [Configure In Lync Server 2013 中的 CAC 的網路網站](lync-server-2013-configure-network-sites-for-cac.md) 。
    
    <div>
    

    > [!NOTE]  
    > 對 ITSP 而言，此網路網站組態沒有作用。 頻寬原則值實際是在步驟 2 套用。

    
    </div>

2.  針對您在步驟 1 建立的網站使用相關的參數值，建立 SIP 主幹的網站間連結。 例如，您可以使用企業中網路網站的名稱作為 NetworkSiteID1 參數的值，並以 ITSP 網路網站作為 NetworkSiteID2 參數的值。 如需詳細資訊，請參閱部署檔中的在 [Lync Server 2013 中建立網路網站間原則](lync-server-2013-create-network-intersite-policies.md) 。 另請參閱 Lync Server 管理命令介面檔，以取得 New-CsNetworkInterSitePolicy Cmdlet。

3.  從 ITSP 取得會話邊界控制器的 (SCB) 媒體端接點的 IP 位址。 將該子網路遮罩為32的 IP 位址，新增至代表 ITSP 的網路網站。 如需詳細資訊，請參閱 [在 Lync Server 2013 中建立子網與網路網站的關聯](lync-server-2013-associate-a-subnet-with-a-network-site.md)。

</div>

<span> </span>

</div>

</div>

</div>

