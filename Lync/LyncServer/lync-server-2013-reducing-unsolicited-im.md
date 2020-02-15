---
title: Lync Server 2013： 減少來路不明的 IM
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reducing unsolicited IM for Lync Server 2013
ms:assetid: d2998708-e699-4465-a918-e1d9ea4c49c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518335(v=OCS.15)
ms:contentKeyID: 62625493
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5574930d6474a75ca4a35219df7cd2e3e2431b15
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050125"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reducing-unsolicited-im-for-lync-server-2013"></a>Lync Server 2013 的減少來路不明的 IM

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-12-05_

智慧型 IM 篩選器應用程式可協助保護您的 Microsoft Lync Server 2013 部署使用最少的使用者經驗降低最常見的病毒。 智慧型 IM 篩選器提供下列功能：

  - 增強型 URL 篩選

  - 增強型檔案傳輸篩選

使用智慧型 IM 篩選器可以設定篩選器，以封鎖來自企業防火牆外部未知端點之來路不明或潛在有害的立即訊息。 您可以指定用於判斷應封鎖之項目的條件來設定篩選器，例如封鎖內含超連結或具特定副檔名之檔案的即時訊息。

部署智慧型 IM 篩選器的應用程式之前，您應先了解如何篩選選項郵件從一個 Lync Server 2013 伺服器路由傳送至另一個時，會套用。 無論伺服器位於單一組織內，或是涵蓋多個組織界限，套用這些篩選選項的方式是一樣的。 這種一致性適用於自訂通知和警告文字插入訊息及跨伺服器傳送的方式。

建議的篩選選項是允許含有超連結的立即訊息，但要求智慧型 IM 篩選器在該連結前面插入底線來停用連結。如果選擇這個選項，您還可以另外撰寫要在每條含有超連結之立即訊息開頭出現的使用者通知。

第二個篩選選項可允許含有未修改超連結的立即訊息。如果您選擇這個選項，則可以另外撰寫 (建議使用) 會插入在每一條訊息中的使用者警告。

第三個選項可封鎖所有包含超連結的立即訊息。如果您選擇這個選項，伺服器就會傳送警告給使用者。您必須撰寫這個警告。

</div>

<span> </span>

</div>

</div>

</div>

