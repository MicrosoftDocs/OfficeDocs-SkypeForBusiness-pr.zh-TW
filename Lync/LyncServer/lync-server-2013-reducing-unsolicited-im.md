---
title: Lync Server 2013：減少來路不明的 IM
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Reducing unsolicited IM for Lync Server 2013
ms:assetid: d2998708-e699-4465-a918-e1d9ea4c49c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518335(v=OCS.15)
ms:contentKeyID: 62625493
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5042c4400cdf16be650a3c2c74ed756f01d93114
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974415"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reducing-unsolicited-im-for-lync-server-2013"></a>減少 Lync Server 2013 來路不明的 IM

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-12-05_

智慧 IM 篩選應用程式可協助保護您的 Microsoft Lync Server 2013 部署，以防範最常見的病毒，讓使用者體驗的效能降至最低。 [智慧 IM] 篩選提供下列功能：

  - 增強的 URL 篩選

  - 增強的檔案傳輸篩選

使用智慧 IM 篩選來設定篩選器，以封鎖來自公司防火牆以外的來自未知端點的未經請求或可能有害的立即訊息。 您可以透過指定準則來決定要封鎖哪些專案（例如包含超連結的立即訊息，以及具有特定副檔名的檔案），來設定篩選。

在您部署智慧 IM 訊息篩選應用程式之前，您應該瞭解當郵件從一個 Lync Server 2013 伺服器路由到另一個時，如何套用篩選選項。 套用這些篩選選項的方式是一致的，不論伺服器是位於單一組織中，還是跨組織界限。 這種一致性會套用至將自訂通知及警告文字插入郵件中並在伺服器之間傳送的方式。

[建議篩選] 選項可讓您在立即訊息中使用超連結，但必須先在其前面插入一個底線，才能停用連結。 如果您選擇此選項，您可以使用額外的選項，在每個包含超連結的立即訊息開頭顯示一則使用者。

第二個篩選選項是允許含有未修改超連結的立即訊息。 如果您選擇此選項，您會有額外選項（建議），給插入在每封郵件中的使用者撰寫警告。

第三個選項是封鎖所有包含超連結的立即訊息。 如果您選擇此選項，伺服器會將警告傳送給使用者。 您必須撰寫此警告。

</div>

<span> </span>

</div>

</div>

</div>

