---
title: Lync Server 2013： 執行綜合交易
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running synthetic transactions
ms:assetid: 2b56c7bd-8956-4fa1-8232-1876b959b258
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720911(v=OCS.15)
ms:contentKeyID: 63969593
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 476223c1c81f6927a1b5f96a78091e0f3c57ea12
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182756"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="running-synthetic-transactions-in-lync-server-2013"></a>在 Lync Server 2013 中執行的綜合交易

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2014年-08-18_

綜合交易通常是以兩種方式進行。 您可以使用 CsHealthMonitoringConfiguration cmdlet 設定的測試使用者，其登錄器集區的每個。 這些測試使用者是一組已預先設定的綜合交易，搭配使用的使用者。 （通常是這些是測試帳戶並不屬於實際使用者的帳戶）。與集區設定的測試使用者，您可以執行的綜合交易針對該集區不必指定的身分識別 （和提供的認證） 測試中所涉及的使用者帳戶。

或者，您可以使用的實際使用者帳戶執行的綜合交易。 例如，如果兩個使用者不能交換立即訊息，您無法執行綜合交易 （而不一組測試帳戶），使用這些兩個使用者帳戶，然後再試以診斷並解決問題。 如果您決定要進行使用實際使用者帳戶的綜合交易，您必須提供登入名稱和每個使用者的密碼。

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中設定監看員節點測試使用者與組態設定](lync-server-2013-configuring-watcher-node-test-users-and-configuration-settings.md)  
[Lync Server 2013 中的綜合交易的特殊設定指示](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

