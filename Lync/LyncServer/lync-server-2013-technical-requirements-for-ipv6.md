---
title: Lync Server 2013 IPv6 的技術需求
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
ms.openlocfilehash: e0688319a1b37dbd609a2f2051b3b8c6dfc6a2d4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746533"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-ipv6-in-lync-server-2013"></a>Lync Server 2013 中 IPv6 的技術需求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-30_

如果您打算為 IPv6 設定 Lync Server 2013，請記住下列需求：

  - 若要將 IPv6 位址搭配 Lync Server 使用，您需要針對必須發現並解析為 IPv6 位址的記錄，建立網域名稱系統（DNS）記錄。 IPv6 DNS 使用主機 AAAA （四 A）記錄。 如果您在部署中同時使用 IPv4 和 IPv6，最好是針對 IPv6 與主機 AAAA 記錄，設定及維護主機 A 記錄。 即使您將部署完全轉換為 IPv6，您仍然可能需要仍使用 IPv4 之外部使用者的 IPv4 DNS 主機記錄。
    
    您可以先部署 IPv6 DNS 主機記錄，然後再開始使用 IPv6。 如果用戶端或伺服器不使用 IPv6，將不會參照該記錄。 轉場技術將根據轉換技術設定與原則，決定要使用哪一筆記錄。

  - 每個 IPv6 位址都有一個範圍。 您可以用來進行 IPv6 定址的三個作用域是 IPv6 全域位址（類似公用 IPv4 位址）、IPv6 唯一本機位址（類似于專用 IPv4 位址範圍），以及 IPv6 鏈路本機位址（類似中的自動私人 IP 位址）適用于 IPv4 的 Windows Server）。 一個池內的所有伺服器都應該有相同範圍的 IPv6 位址。

<div>


> [!IMPORTANT]  
> IPv6 是一個複雜的主題，需要謹慎規劃您的網路小組和 Internet 提供者，以協助確保您在 Windows Server 層級和 Lync Server 2013 層級指派的位址如期運作。 如需有關 IPv6 定址與規劃的其他資源，請參閱本主題結尾的連結。



</div>

<div>

## <a name="see-also"></a>請參閱


[IP 版本6定址架構](http://tools.ietf.org/html/rfc4291)  
[IPv6 全域單播位址格式](http://tools.ietf.org/html/rfc3587)  
[唯一的局部 IPv6 單播位址](http://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

