---
title: Lync Server 2013：執行綜合交易
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Running synthetic transactions
ms:assetid: 2b56c7bd-8956-4fa1-8232-1876b959b258
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720911(v=OCS.15)
ms:contentKeyID: 63969593
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 489b8a02d829f4f12038e3f07559166c1c015b80
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976035"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-synthetic-transactions-in-lync-server-2013"></a>在 Lync Server 2013 中執行綜合交易

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-08-18_

綜合交易通常是以兩種方式執行。 您可以使用 CsHealthMonitoringConfiguration Cmdlet，為每個註冊機構池設定測試使用者。 這些測試使用者是預先設定為與綜合交易搭配使用的一組使用者。 （通常，這些是測試帳戶，而不是屬於實際使用者的帳戶。）在針對某個池設定測試使用者的情況下，您可以針對該池執行綜合交易，而不必指定測試中所涉及之使用者帳戶的身分識別（並提供認證）。

或者，您可以使用實際的使用者帳戶來執行綜合交易。 例如，如果兩個使用者無法交換立即訊息，您可以使用這兩個使用者帳戶（而不是一副測試帳戶）來執行綜合交易，然後嘗試診斷並解決問題。 如果您決定使用實際的使用者帳戶來執行綜合交易，您必須為每位使用者提供登入名稱和密碼。

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中設定觀察程式節點測試使用者和配置設定](lync-server-2013-configuring-watcher-node-test-users-and-configuration-settings.md)  
[Lync Server 2013 中的綜合交易的特殊設定指示](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

