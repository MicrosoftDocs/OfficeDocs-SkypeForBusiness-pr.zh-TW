---
title: Lync Server 2013 的 IPv6 的技術需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for IPv6
ms:assetid: caff0123-ce41-4a62-87a0-00b1d118b72b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205278(v=OCS.15)
ms:contentKeyID: 48185465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a5565080f2b5fab0f47cc944f9569f55e8721c4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194886"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-ipv6-in-lync-server-2013"></a>Lync Server 2013 中的 IPv6 的技術需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-30_

如果您打算針對 IPv6 設定 Lync Server 2013，請注意下列需求：

  - 若要使用 IPv6 位址與 Lync Server，您需要建立網域名稱系統 (DNS) 記錄的記錄，必須能夠探索及解析至 IPv6 位址。 IPv6 DNS 使用主機 AAAA (四 A) 記錄。 如果您部署中使用 IPv4 和 IPv6，最好是設定及維護主機 A 記錄的 IPv4 和 IPv6 的主機 AAAA 記錄。 即使當您完全部署轉換到 IPv6，您可能仍需要 IPv4 DNS 主機記錄仍在使用 IPv4 的外部使用者。
    
    在您開始使用 IPv6 之前，您可以部署 IPv6 DNS 主機記錄。 如果用戶端或伺服器不會使用 IPv6，就不會參考記錄。 過渡時期技術會使若要使用，記錄決策轉換技術組態與原則為基礎。

  - 每個 IPv6 位址具有範圍。 您可以使用 IPv6 定址的三個範圍是 IPv6 全域位址 （類似公用 IPv4 位址）、 IPv6 唯一本機位址 （類似私人 IPv4 位址範圍），以及 IPv6 連結本機位址 （類似於自動私人 IP 位址Windows Server 的 IPv4)。 集區中的所有伺服器都應有相同範圍的 IPv6 位址。

<div>


> [!IMPORTANT]  
> IPv6 是複雜的主題，必須進行審慎規劃您的網路小組與您的網際網路提供者，以協助確保您指定 Windows 伺服器層級和 Lync Server 2013 層級的地址，如預期般運作。 請參閱此主題末端的連結，以取得 IPv6 位址指定和規劃的其他資源。



</div>

<div>

## <a name="see-also"></a>另請參閱


[IP 版本 6 定址架構](https://tools.ietf.org/html/rfc4291)  
[IPv6 全域單點傳播位址格式](https://tools.ietf.org/html/rfc3587)  
[唯一本機 IPv6 單點傳播位址](https://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

