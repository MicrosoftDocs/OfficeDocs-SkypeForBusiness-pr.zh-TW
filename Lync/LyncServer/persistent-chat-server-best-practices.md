---
title: 常設聊天室伺服器最佳作法
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Persistent Chat Server best practices
ms:assetid: dc18e7f7-599b-4d32-abf7-cd9e691426a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398970(v=OCS.15)
ms:contentKeyID: 48185612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10790495f38a469218e00f6906cad589f96c57e5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034453"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="persistent-chat-server-best-practices"></a>常設聊天室伺服器最佳作法

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-10-06_

當您建立類別和常設聊天室並且設計範圍與成員資格時，下列秘訣可協助您規劃：

  - 如果貴公司不需要道德管束，不會逐漸類別樹狀目錄中的範圍。 置於一個類別的範圍中的所有使用者，並建立該類別中的所有聊天室。 接下來，使用僅限成員資格清單來授與或限制每個聊天室的存取。

  - 在大多數情況下，您應讓使用者能夠建立新聊天室，以便關於新主題的討論區可以啟動隨時。 執行此動作，以列出**AllowedMembers**清單相同的**建立者**。 不過，如果您想要允許只有中央支援小組或指定要建立之聊天室的使用者，然後進行**Creators**清單為適當的子集。

  - 授與每個聊天室的完整名稱和說明，摘要說明其中它的方式符合您的組織。 因為使用者無法查看的類別名稱，在使用聊天室時，您無法仰賴以協助使用者決定預定的討論論壇聊天室的類別名稱。

  - 您可能想要有自訂聊天室建立工作流程，如果您有特定的命名慣例或其他的存取控制或實作驗證。 常設聊天室組態可讓您自訂**RoomManagementUrl**成您主控。 例如，當使用者按一下其 Lync 用戶端中**建立會議室**，他們可以重新導向至您的自訂解決方案。

  - 建立各種不同的增益集，以將文字方塊帶到聊天室其他商務資料中增強的聊天室的經驗。 系統管理員必須註冊他們想要允許系統中的增益集。 聊天室管理員及建立者可以選擇從允許的增益集至其各自的會議室最相關的清單。

<div>

## <a name="see-also"></a>另請參閱


[管理類別、 聊天室及 Lync Server 2013 中增益集](lync-server-2013-managing-categories-rooms-and-add-ins.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

