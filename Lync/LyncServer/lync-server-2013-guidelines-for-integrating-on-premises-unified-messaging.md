---
title: Lync Server 2013：整合內部部署整合通訊的指導方針
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Guidelines for integrating on-premises Unified Messaging and Lync Server
ms:assetid: 829ac017-6907-40f9-be22-787a28eae0ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398656(v=OCS.15)
ms:contentKeyID: 48184681
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 71d6fc97a0b8c96758344dea12a0720d5ad049ed
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214280"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="guidelines-for-integrating-on-premises-unified-messaging-and-lync-server-2013"></a>整合內部部署整合通訊和 Lync Server 2013 的指導方針

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-25_

以下是部署企業語音時所需考慮的指導方針和最佳作法：

<div>


> [!IMPORTANT]  
> 只有在您同時使用 UCMA 4 時，Exchange 整合通訊 (UM) 才會支援 IPv6。



</div>

  - 部署 Lync Server 2013 Standard Edition Server 或前端集區。 如需安裝的詳細資訊，請參閱部署檔中的[部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md) 。

  - 與 Exchange 系統管理員合作，確認每一個人將要執行的工作，以確保能夠順暢、成功地整合。

  - 在您要為 Exchange UM 啟用使用者的每個 Exchange 整合通訊 (UM) 樹系中，部署 Exchange 信箱伺服器角色。 如需安裝 Exchange 伺服器角色的詳細資訊，請參閱 Microsoft Exchange Server 2013 檔。
    
    <div>
    

    > [!IMPORTANT]  
    > 安裝 Exchange 整合通訊 (UM) 時，會將其設定為使用自我簽署憑證。<BR>不過，自我簽署憑證不會讓 Lync Server 2013 和 Exchange UM 彼此信任，這就是為何必須從兩部伺服器信任的憑證授權單位單位要求個別憑證。

    
    </div>

  - 如果 Lync Server 2013 和 Exchange UM 安裝在不同的樹系中，請將每個 Exchange 樹系設定為信任 Lync Server 2013 樹系和 Lync Server 2013 樹系，以信任每個 Exchange 樹系。 此外，您也可以在 Lync Server 2013 樹系中的使用者物件上設定使用者的 Exchange UM 設定，通常是使用腳本或跨樹系工具（例如身分識別生命週期管理員 (ILM) ）。

  - 必要時，安裝 Exchange 管理主控台以便管理 Unified Messaging 伺服器。

  - 取得 Outlook Voice Access 和自動語音應答的有效電話號碼。

  - 如果您使用的 Exchange UM 版本低於 Microsoft Exchange Server 2010 Service Pack 1 (SP1) ，則為 Exchange UM SIP URI 撥號對應表和 Enterprise Voice 撥號對應表的座標名稱。

<div>

## <a name="deploying-redundant-exchange-um-servers"></a>部署重複的 Exchange UM 伺服器

<div>


> [!IMPORTANT]  
> 建議您為組織設定的每個 Exchange UM SIP URI 撥號對應表，至少部署兩部執行 Exchange UM 服務的伺服器。 除了提供擴充的容量之外，部署冗余伺服器也可提供高可用性。 當伺服器失敗時，Lync Server 2013 可以設定成容錯移轉至另一部伺服器。



</div>

以下範例設定可提供 Exchange UM 恢復能力。

**範例 1：Exchange UM 恢復能力**

![Exchange UM 範例1](images/Gg398656.3644b847-0847-4550-a989-e3fc51de5c4b(OCS.15).jpg "Exchange UM 範例1")

在範例 1 中，Tukwila 資料中心內的 Exchange UM 伺服器 1 和伺服器 2 均已啟用；Dublin 資料中心內的 Exchange UM 伺服器 3 和伺服器 4 均已啟用。 在 Tukwila 中發生 Exchange UM 中斷的情況時，網域名稱系統 (DNS) 伺服器1和2的記錄應該設定為分別指向 servers 3 和4。 在都柏林中發生 Exchange UM 中斷的情況時，伺服器3和4的 DNS A 記錄應該設定為分別指向 servers 1 和2。

<div>


> [!NOTE]  
> 在範例 1 中，您還需要在每部 Exchange UM 伺服器上指派以下任一憑證： 
> <UL>
> <LI>
> <P>在主體替代名稱 (SAN) 中使用含萬用字元的憑證。</P>
> <LI>
> <P>將 SAN 中每四個 Exchange UM 伺服器的完整功能變數名稱 (FQDN) 放入該功能變數名稱。</P></LI></UL>



</div>

**範例 2：Exchange UM 恢復能力**

![Exchange UM 範例2](images/Gg398656.15754273-306e-448d-b258-84bc2936a2e8(OCS.15).jpg "Exchange UM 範例2")

在範例 2 中，於正常運作情況下，Tukwila 資料中心內的 Exchange UM 伺服器 1 和伺服器 2 均已啟用；Dublin 資料中心內的 Exchange UM 伺服器 3 和伺服器 4 均已啟用。這四部伺服器均包含在 Tukwila 使用者的 SIP URI 撥號對應表中，不過伺服器 3 和 4 均已停用。當 Tukwila 的 Exchange UM 伺服器發生如停止運作等的情況時，應停用 Exchange UM 伺服器 1 和 2 並啟用 Exchange UM 伺服器 3 和 4，以將 Tukwila Exchange UM 的流量路由傳送至 Dublin 的伺服器。

如需如何啟用或停用 Exchange 2013 整合通訊的詳細資訊，請參閱「整合 Exchange 2013 UM 搭配 Lync Server」 [https://go.microsoft.com/fwlink/p/?LinkId=265372](https://go.microsoft.com/fwlink/p/?linkid=265372) 。

如需如何在 Microsoft Exchange Server 2010 上啟用或停用整合通訊的詳細資訊，請參閱：

  - 「在 Exchange 2010 上啟用整合通訊」 [https://go.microsoft.com/fwlink/p/?LinkId=204418](https://go.microsoft.com/fwlink/p/?linkid=204418) 。

  - 「在 Exchange 2010 上停用整合通訊」 [https://go.microsoft.com/fwlink/p/?LinkId=204416](https://go.microsoft.com/fwlink/p/?linkid=204416) 。

</div>

<div>

## <a name="see-also"></a>另請參閱


[整合內部部署整合通訊和 Lync Server 2013 的部署程式](lync-server-2013-deployment-process-for-integrating-on-premises-unified-messaging.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

