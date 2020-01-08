---
title: Lync Server 2013：前端集區配對資料安全性
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Front End pool pairing data security
ms:assetid: edb852b8-ea86-4948-b756-60fe6ee876d2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721930(v=OCS.15)
ms:contentKeyID: 49733865
ms.date: 10/07/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: db1a408aecedc14162271d5def1adc2bcebdfd82
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977170"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="front-end-pool-pairing-data-security-in-lync-server-2013"></a>Lync Server 2013 中前端集區配對資料安全性

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-10-07_

備份服務是在 Lync Server 2013 中引入的資料複製機制，可在兩個資料中心之間連續傳送使用者資料和會議內容，以進行災害復原。 使用者資料包含使用者 SIP Uri 以及連絡人清單和設定。 會議內容包括 Microsoft PowerPoint 2010 上傳，以及在會議中使用的白板。 從來源池中，使用者資料和會議內容是從本機存儲區（zipped）匯出到目標池，並將其解壓縮並匯入到本機儲存區。 備份服務假設兩個資料中心之間的通訊連結位於從網際網路保護的公司網路內。 它不會對兩個資料中心之間的傳輸資料進行加密，也不會將它本身封裝在安全通訊協定（例如 HTTPS）中。 因此，來自公司網路內部人員的中間人攻擊是可能的。

<div>

## <a name="evaluating-security-risks"></a>評估安全風險

跨多個資料中心部署 Lync Server 2013 並使用災害復原功能的任何企業，都必須確保跨資料中心流量受到其公司內部網路的保護。 考慮內部攻擊防護的企業必須保護資料中心間的通訊連結。

假設企業的資料中心受保護在公司內部網路的後面是標準的。 在這些資料中心中傳送了許多其他類型的公司機密資料。 如果這些跨資料中心連結未受到保護，企業的 IT 基礎結構就會 dire 風險。

雖然在商業網路中存在中間人攻擊的風險，但與公開網路流量相比，它相對包含。 具體來說，由備份服務所公開的使用者資料（例如 SIP Uri），通常可透過其他方法（例如 Exchange 或其他目錄軟體的全域通訊錄）來提供給公司內的所有員工。 因此，當您使用備份服務在兩個配對的池中複製資料時，重點應該是保護兩個資料中心之間的 WAN。

</div>

<div>

## <a name="mitigating-security-risks"></a>減輕安全性風險

您可以透過多種方式來加強備份服務流量的安全性保護，包括限制存取資料中心，以保護兩個資料中心之間的 WAN 傳輸。 在大多數情況下，部署 Lync Server 2013 的企業可能已經有必要的安全性基礎結構。 針對尋求指導方針的企業，Microsoft 提供的解決方案就是建立安全 IT 基礎結構的範例。 不過，這並不表示它是唯一的解決方案，也不會暗示它是 Lync Server 的首選方案。 我們建議企業客戶根據其 IT 安全基礎結構和需求，選擇適合其特定需求的方案。Microsoft 解決方案範例使用 IPSec 和群組原則進行伺服器與網域隔離。 如需詳細資訊[http://go.microsoft.com/fwlink/p/?LinkId=268544](http://go.microsoft.com/fwlink/p/?linkid=268544)，請參閱。 如需問題和批註，請與 secwish@microsoft.com。

另一種可能的解決方法是使用 IPSec 來協助保護備份服務本身所傳送的資料。 如果您選擇這個方法，您應該針對下列伺服器設定 SMB 通訊協定的 IPSec 規則，其中池 A 和池 B 都是兩個配對的前端池。

  - 從 Pool A 中的每個前端伺服器到池 B 所使用之檔案存放區的 SMB 服務（TCP/445）。

  - 從 Pool B 中的每個前端伺服器到 Pool A 所使用之檔案存放區的 SMB 服務（TCP/445）。

<div>


> [!WARNING]  
> IPsec 不是用來取代應用程式層級安全性，例如 SSL/TLS。 使用 IPsec 的其中一個優點是，它可以提供現有應用程式的網路流量安全性，而不需變更它們。 只要想要保護兩個資料中心間傳輸的企業，就應該諮詢其各自的網路硬體廠商，瞭解如何使用供應商的裝置來設定安全的 WAN 連線。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

