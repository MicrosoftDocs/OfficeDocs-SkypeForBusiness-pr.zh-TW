---
title: Lync Server 2013 IPv6 的技術需求
description: Lync Server 2013 IPv6 的技術需求。
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
ms.openlocfilehash: c54dfbdba56c45f19e7664db075331591c8e87cc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559459"
---
# <a name="technical-requirements-for-ipv6-in-lync-server-2013"></a>Lync Server 2013 中 IPv6 的技術需求

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-30_

如果您打算為 IPv6 設定 Lync Server 2013，請牢記下列需求：

  - 若要使用 Lync Server 的 IPv6 位址，您必須為必須探索並解析為 IPv6 位址的記錄，建立網域名稱系統 (DNS) 記錄。 IPv6 DNS 使用主機 AAAA (四 A) 記錄。 如果您在部署中同時使用 IPv4 和 IPv6，最好是設定及維護主機 A 記錄，以供 IPv6 的 IPv4 和裝載 AAAA 記錄。 即使您完全將部署轉換為 IPv6，您仍然可能需要 IPv4 仍在使用 IPv4 的外部使用者的 DNS 主機記錄。
    
    您可以在開始使用 IPv6 之前，先部署 IPv6 的 DNS 主機記錄。 如果用戶端或伺服器不使用 IPv6，將不會參照記錄。 過渡技術會根據轉換技術設定和原則，決定要使用哪個記錄。

  - 每個 IPv6 位址都有一個範圍。 您可以用於 IPv6 定址的三個範圍是 IPv6 的全域位址 (類似公用 IPv4 位址) 、IPv6 唯一本機位址 (類似專用 IPv4 位址範圍) ，以及 IPv6 連結本機位址 (類似于 Windows Server 中 IPv4) 的自動私人 IP 位址。 集區中的所有伺服器都應有相同範圍的 IPv6 位址。

<div>


> [!IMPORTANT]  
> IPv6 是一個複雜的主題，需要仔細規劃網路小組和 Internet 提供者，以協助確保您在 Windows Server 層級和 Lync Server 2013 層級所指派的位址如期運作。 請參閱此主題末端的連結，以取得 IPv6 位址指定和規劃的其他資源。



</div>

<div>

## <a name="see-also"></a>另請參閱


[IP 版本6定址架構](https://tools.ietf.org/html/rfc4291)  
[IPv6 全域單路廣播位址格式](https://tools.ietf.org/html/rfc3587)  
[唯一的本地 IPv6 單播位址](https://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

