---
title: Lync Server 2013：執行綜合交易
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
ms.openlocfilehash: 297e1ee6416fb534791a2459e10acaa87f86e205
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511090"
---
# <a name="running-synthetic-transactions-in-lync-server-2013"></a>在 Lync Server 2013 中執行綜合交易

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-08-18_

綜合交易通常會以兩種方式執行。 您可以使用 CsHealthMonitoringConfiguration Cmdlet 為每個註冊機構集區設定測試使用者。 這些測試使用者是一組預先設定為搭配綜合交易使用的使用者。  (通常是測試帳戶，而不是屬於實際使用者的帳戶。 ) 搭配針對集區設定的測試使用者，您可以針對該集區執行綜合交易，而不必指定 (的身分識別，並提供認證，以) 測試所涉及的使用者帳戶。

或者，您可以使用實際的使用者帳戶執行綜合交易。 例如，如果兩位使用者無法 exchange 立即訊息，您可以使用這兩個使用者 (帳戶執行綜合交易，而不是) 一對測試帳戶，然後嘗試診斷並解決問題。 如果您決定使用實際使用者帳戶進行綜合交易，您必須為每位使用者提供登入名稱和密碼。

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中設定監視節點測試使用者和設定設定](lync-server-2013-configuring-watcher-node-test-users-and-configuration-settings.md)  
[Lync Server 2013 中綜合交易的特殊設定指示](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

