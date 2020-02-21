---
title: Lync Server 2013： 前端集區配對資料安全性
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
ms.openlocfilehash: 503a5a02d4412fe2bbbf5f1882e3d7d117640576
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206559"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="front-end-pool-pairing-data-security-in-lync-server-2013"></a>前端配對 Lync Server 2013 中的資料安全性集區

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-10-07_

備份服務是在兩個配對的前端集區，持續跨兩個資料中心的災害復原用途之間傳輸使用者資料和會議內容的 Lync Server 2013 中引進的資料複寫機制。 使用者資料包含使用者的 SIP Uri，以及連絡人清單和設定。 會議內容包含 Microsoft PowerPoint 2010 上傳，以及在會議中使用的白板。 從來源集區、 使用者資料和會議內容會匯出從本機儲存體、 zipped、 轉接至目標集區，它是在其中顯示解壓縮並匯入至本機儲存體。 備份服務假設兩個資料中心之間的通訊連結會受到網際網路從公司網路內。 它不會加密的兩個資料中心之間轉送的資料，也不其原生封裝在一個安全的通訊協定，例如 HTTPS。 因此，從公司網路內的內部人員攔截攻擊可能會。

<div>

## <a name="evaluating-security-risks"></a>評估安全性風險

跨多個資料中心部署 Lync Server 2013，並使用災害復原功能任何企業必須確定該跨資料中心流量受到其公司內部網路。 關於內部攻擊保護哪些照護必須保護資料中心之間的通訊連結企業版。

企業版的資料中心會受到保護公司內部網路背後的假設是標準。 有許多其他類型的公司在這些資料中心間傳輸的機密資料。 企業的 IT 基礎結構是可怕風險，如果未受到保護這些跨資料中心的連結。

雖然攻擊的風險，攔截位在公司網路內已存在，它是相當包含與公開至網際網路的流量。 具體而言，（例如 SIP Uri) 的備份服務所公開的使用者資料是通常可透過其他方式，例如 Exchange 或其他目錄軟體全域通訊錄公司內的所有員工。 因此，焦點應該在保護備份服務是用來將兩個配對集區之間的資料複製兩個資料中心間的 WAN。

</div>

<div>

## <a name="mitigating-security-risks"></a>減輕安全性風險

有許多方法來加強安全性保護備份服務的流量，範圍從限制存取權來保護 WAN 的資料中心兩個資料中心之間傳輸。 在大多數情況下，部署 Lync Server 2013 的企業可能中已有必要的安全性基礎結構的地方。 尋找下列項目的指引企業版，Microsoft 會提供如何建立安全的 IT 基礎結構的範例方案。 不過，這並不表示它是唯一的解決方案，也不表示它是 Lync Server 的較佳的解決方案。 建議企業客戶選擇解決方案符合其特定需求，根據其 IT 安全性基礎結構與需求。範例 Microsoft solution 採用 IPSec 」 和 「 群組原則的伺服器和為了隔離網域。 如需詳細資訊，請參閱[https://go.microsoft.com/fwlink/p/?LinkId=268544](https://go.microsoft.com/fwlink/p/?linkid=268544)。 問題和註解，請連絡 secwish@microsoft.com。

其他可能的解決方案是使用 IPSec 目的只是為了協助確保備份服務傳送本身的資料安全。 如果您選擇此方法時，您應該設定為下列的伺服器，其中的集區和集區 B 是兩個配對的前端集區的 SMB 通訊協定的 IPSec 規則。

  - SMB (TCP/445) 從服務每個前端伺服器集區的檔案存放區使用的集區 b。

  - SMB (TCP/445) 從服務每個前端伺服器集區 B 至集區 a 所使用檔案存放區

<div>


> [!WARNING]  
> IPsec，不得為應用程式層級安全性，例如 SSL/TLS 的替代文字。 使用 IPsec 的一項優點是可以提供網路流量安全之現有應用程式而不必將它們變更。 想要只之間安全傳輸兩個資料中心的企業應諮詢其各自的網路硬體廠商有關使用供應商的設備來設定安全的 WAN 連線的方式。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

