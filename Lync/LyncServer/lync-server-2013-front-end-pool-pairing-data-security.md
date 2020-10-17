---
title: Lync Server 2013：前端集區配對資料安全性
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Front End pool pairing data security
ms:assetid: edb852b8-ea86-4948-b756-60fe6ee876d2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721930(v=OCS.15)
ms:contentKeyID: 49733865
ms.date: 10/07/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d86f60e81e053a1ba07878728dd9c7273bd7feeb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500720"
---
# <a name="front-end-pool-pairing-data-security-in-lync-server-2013"></a>Lync Server 2013 中的前端集區配對資料安全性

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-10-07_

備份服務是 Lync Server 2013 中引入的資料複寫機制，可持續跨兩個資料中心，將兩個配對前端集區間的使用者資料和會議內容傳輸到兩個資料中心，以進行嚴重損壞修復。 使用者資料包含使用者 SIP URIs 以及連絡人清單和設定。 會議內容包括 Microsoft PowerPoint 2010 上傳，以及在會議中使用的白板。 從來源集區中，使用者資料和會議內容會從本機儲存區（已壓縮）匯出至目標集區，並將其解壓縮並匯入至本機儲存區。 備份服務假定兩個資料中心之間的通訊連結，都位於從網際網路保護的公司網路內。 它不會加密兩個資料中心之間已傳輸的資料，也不會在本機封裝在安全通訊協定（例如 HTTPS）內。 因此，來自公司網路內部的內部人員可以進行中間人攻擊。

<div>

## <a name="evaluating-security-risks"></a>評估安全性風險

任何可跨多個資料中心部署 Lync Server 2013 並使用嚴重損壞修復功能的企業，都必須確保跨資料中心的流量受到公司內部網路的保護。 關心內部攻擊防護的企業必須保護資料中心之間的通訊連結。

假設企業的資料中心受保護在公司內部網路的背後是標準的。 在這些資料中心內，有許多其他類型的公司機密資料會傳輸。 如果這些跨資料中心連結未受到保護，企業的 IT 基礎結構便會 dire 風險。

雖然公司網路記憶體在中間人攻擊的風險存在，但是它相對於公開網際網路的流量，其相對包含。 尤其是備份服務所公開的使用者資料 (例如 SIP URIs) ，通常可透過其他方式（如 Exchange 或其他目錄軟體的全域通訊錄），從公司內的所有員工取得。 因此，當備份服務用於複製兩個配對集區間的資料時，重點應該是保護兩個資料中心之間的 WAN。

</div>

<div>

## <a name="mitigating-security-risks"></a>降低安全性風險

有許多方式可以增強備份服務流量的安全性保護，其範圍包括限制存取資料中心，以保護兩個資料中心之間的 WAN 傳輸。 在大多數情況下，部署 Lync Server 2013 的企業可能已具備必要的安全性基礎結構。 針對尋求指導的企業，Microsoft 提供的解決方案是如何建立安全 IT 基礎結構的範例。 不過，這並不表示這是唯一的解決方案，也不表示它是 Lync Server 的慣用方案。 我們建議企業客戶根據其 IT 安全性基礎結構和需求，選擇可滿足其特定需求的解決方案。Microsoft 解決方案範例使用 IPSec 和群組原則來進行伺服器和網域隔離。 如需詳細資訊，請參閱 [https://go.microsoft.com/fwlink/p/?LinkId=268544](https://go.microsoft.com/fwlink/p/?linkid=268544) 。 如需問題和批註，請與 secwish@microsoft.com 聯繫。

另一種可能的解決方法是使用 IPSec，協助保護備份服務本身所傳送的資料。 如果您選擇此方法，則應該為下列伺服器（其中集區 A 與集區 B 是兩個成對的前端集區）設定 SMB 通訊協定的 IPSec 規則。

  - SMB 服務 (TCP/445) 從集區 A 中的每一部前端伺服器到集區 B 所使用的檔案存放區。

  - SMB 服務 (TCP/445) 從集區 B 中的每一部前端伺服器到集區 A 所使用的檔案存放區。

<div>


> [!WARNING]  
> IPsec 不會做為應用程式層級安全性的取代，例如 SSL/TLS。 使用 IPsec 的其中一個優點是，它可以為現有的應用程式提供網路流量安全性，而不需要加以變更。 只想要將兩個資料中心之間的傳輸安全的企業，應諮詢其各自的網路硬體廠商，以瞭解使用廠商的設備設定安全的 WAN 連線的方式。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

