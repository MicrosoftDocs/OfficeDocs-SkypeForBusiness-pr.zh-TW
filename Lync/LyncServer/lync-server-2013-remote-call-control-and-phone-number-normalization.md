---
title: Lync Server 2013：遠端呼叫控制和電話號碼標準化
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remote call control and phone number normalization
ms:assetid: 291d9e87-4c65-4ea2-888f-517741391de5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558630(v=OCS.15)
ms:contentKeyID: 48183696
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 211f0f717f7c40895cdbbad75bd98ae0ff90af89
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536550"
---
# <a name="remote-call-control-and-phone-number-normalization-in-lync-server-2013"></a>Lync Server 2013 的遠端呼叫控制和電話號碼正規化

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-22_

Lync 用戶端會下載電話號碼正規化規則，作為通訊錄服務的一部分 (ABS) 檔案下載。 在遠端呼叫控制案例中，通訊錄服務電話號碼正規化規則會同時套用至撥入與撥出的遠端呼叫控制電話。 有來電撥打給已啟用遠端呼叫控制的使用者時，來電者的電話號碼會先由 SIP/CSTA 閘道或專用交換機 (PBX) 正規化為 E.164 格式。 當 Lync Server 2013 接收來自閘道的呼叫時，會針對來電者的 Microsoft Office Outlook 連絡人清單中的標準化號碼，或在通訊錄服務中儲存的全域通訊清單 (GAL) ，對來電者的電話號碼執行反向號碼查閱 (RNL) 。 如果反向號碼查閱順利找到相符項目，則會以來電通知中的名稱識別來電者。

對於撥出的遠端呼叫控制通話，Lync 會在將通話路由傳送至 SIP/CSTA 閘道之前，先將通訊錄服務電話號碼正規化規則套用至撥號的號碼。

如需建立遠端呼叫控制之電話號碼正規化規則的詳細資訊，請參閱規劃檔中的 [Lync Server 2013 中的撥號對應表和正常化規則](lync-server-2013-dial-plans-and-normalization-rules.md) 。

<div>

## <a name="migrating-phone-number-normalization-rules"></a>移轉電話號碼正規化規則

如果您要移轉先前啟用遠端呼叫控制的使用者，請參閱移轉文件中的下列主題：

  - 如需 Lync Server 2010，請參閱遷移檔中的 [遷移通訊錄](migrate-address-book.md) 。

  - 如需通訊伺服器 2007 R2，請參閱遷移檔中的 [遷移通訊錄](migrate-address-book_1.md) 。

</div>

</div>

<span> </span>

</div>

</div>

</div>

