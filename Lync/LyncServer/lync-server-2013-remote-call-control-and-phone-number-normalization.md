---
title: Lync Server 2013：遠端呼叫控制和電話號碼正規化
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Remote call control and phone number normalization
ms:assetid: 291d9e87-4c65-4ea2-888f-517741391de5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558630(v=OCS.15)
ms:contentKeyID: 48183696
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86de318cb1e72fce8fb6f42ff7698db5974034fe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976116"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remote-call-control-and-phone-number-normalization-in-lync-server-2013"></a>Lync Server 2013 中的遠端呼叫控制和電話號碼正規化

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-22_

Lync 用戶端會在通訊錄服務（ABS）檔案下載中下載電話號碼正規化規則。 在遠端通話控制案例中，通訊錄服務電話號碼正規化規則會套用到內送和撥出的遠端通話控制通話。 對於已啟用遠端呼叫控制的使用者，來電的電話號碼會先以 SIP/CSTA 閘道或私人分支交換（PBX）的方式來正常化為. 164 格式。 當 Lync Server 2013 從閘道接收呼叫時，會針對被呼叫者的 Microsoft Office Outlook 連絡人清單或全域通訊清單（GAL）中的標準化數位，在來電者的電話號碼上執行反向號碼查閱（RNL），並儲存在通訊錄服務。 如果 [反向號碼查閱] 成功找到一個相符專案，來電者就會在來電通知中以名稱來加以識別。

對於傳出的遠端通話控制通話，Lync 會在將呼叫傳送到 SIP/CSTA 閘道之前，將通訊錄服務電話號碼正規化規則套用至撥號號碼。

如需建立遠端通話控制的電話號碼正規化規則的詳細資料，請參閱規劃檔中的[Lync Server 2013 中的撥號方案和正常化規則](lync-server-2013-dial-plans-and-normalization-rules.md)。

<div>

## <a name="migrating-phone-number-normalization-rules"></a>遷移電話號碼正規化規則

如果您要將先前啟用的使用者遷移至 [遠端通話] 控制，請參閱以下 [遷移] 檔中的主題：

  - 針對 Lync Server 2010，請參閱遷移檔中的 [[遷移通訊錄](migrate-address-book.md)]。

  - 針對通訊伺服器 2007 R2，請參閱遷移檔中的 [[遷移通訊錄](migrate-address-book_1.md)]。

</div>

</div>

<span> </span>

</div>

</div>

</div>

