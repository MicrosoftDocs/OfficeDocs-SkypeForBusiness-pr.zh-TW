---
title: Lync Server 2013： 遠端呼叫控制和電話號碼正規化
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
ms.openlocfilehash: 7ddf66011a992c9ed306a1fb6652f63133ecb123
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138814"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remote-call-control-and-phone-number-normalization-in-lync-server-2013"></a>遠端呼叫控制和電話號碼正規化 Lync Server 2013 中

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-22_

Lync 用戶端下載通訊錄服務 (ABS) 檔案下載的一部分的電話號碼正規化規則。 在遠端呼叫控制案例中，通訊錄服務電話號碼正規化規則會同時套用至撥入與撥出的遠端呼叫控制電話。 有來電撥打給已啟用遠端呼叫控制的使用者時，來電者的電話號碼會先由 SIP/CSTA 閘道或專用交換機 (PBX) 正規化為 E.164 格式。 當 Lync Server 2013 接收來自閘道的通話時，便會在受話者的 Microsoft Office Outlook 連絡人清單或會儲存在全域通訊清單 (GAL) 中的正規化數字針對來電者的電話號碼執行反向號碼查閱 (RNL)通訊錄服務。 如果反向號碼查閱順利找到相符項目，則會以來電通知中的名稱識別來電者。

對於撥出的遠端呼叫控制電話，Lync 會套用通訊錄服務電話號碼正規化規則之前將電話路由至 SIP/CSTA 閘道對撥打的號碼。

如需建立電話號碼正規化規則為遠端呼叫控制的詳細資訊，請參閱規劃文件中的[撥號對應表和 Lync Server 2013 中的正規化規則](lync-server-2013-dial-plans-and-normalization-rules.md)。

<div>

## <a name="migrating-phone-number-normalization-rules"></a>移轉電話號碼正規化規則

如果您要移轉先前啟用遠端呼叫控制的使用者，請參閱移轉文件中的下列主題：

  - Lync Server 2010，請參閱移轉文件中的[Migrate Address Book](migrate-address-book.md) 。

  - Communications Server 2007 R2，請參閱移轉文件中的[Migrate Address Book](migrate-address-book_1.md) 。

</div>

</div>

<span> </span>

</div>

</div>

</div>

