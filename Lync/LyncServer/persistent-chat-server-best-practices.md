---
title: Persistent Chat Server 最佳作法
description: Persistent Chat Server 最佳作法。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Persistent Chat Server best practices
ms:assetid: dc18e7f7-599b-4d32-abf7-cd9e691426a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398970(v=OCS.15)
ms:contentKeyID: 48185612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c575c0afa0366e88748eadfcf4c04fccb20b375
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571259"
---
# <a name="persistent-chat-server-best-practices"></a>Persistent Chat Server 最佳作法

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-06_

當您建立類別和持續聊天室並設計範圍和成員資格時，下列秘訣可協助您進行規劃：

  - 如果您的公司不需要道德的留言板，請勿縮小類別樹狀目錄中的範圍。 將所有使用者放在一個類別的範圍中，並在該類別中建立所有聊天室。 接著，只使用成員資格清單，授與或限制每個聊天室的存取權。

  - 在大多數情況下，您應該讓使用者能夠建立新的聊天室，以便在任何時間開始有關新主題的討論。 讓建立 **者** 清單與 **AllowedMembers** 清單相同。 不過，如果您只想要讓中央支援小組或指定的使用者建立聊天室，請將建立 **者** 清單當做適當的子集。

  - 提供每個聊天室的完整名稱和描述摘要，說明組織中適合的位置。 由於使用者在使用聊天室時看不到其類別名稱，因此您無法依賴類別名稱來協助使用者決定聊天室的預定討論論壇。

  - 如果您有某些命名慣例或其他的存取控制或驗證實施，您可能想要建立自訂聊天室建立工作流程。 Persistent Chat 設定可讓您自訂 **RoomManagementUrl** 為您裝載的內容。 例如，當使用者按一下其 Lync 用戶端中 **的 [建立會議室** ] 時，即可將其重新導向至您的自訂解決方案。

  - 建立各種增益集，協助您在聊天室中引入其他商務資料，以加強聊天室的體驗。 管理員必須在系統中註冊他們想要允許的增益集。 聊天室管理員和建立者可以從與其各自的聊天室最相關的現有增益集清單中選擇。

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中管理類別、聊天室及增益集](lync-server-2013-managing-categories-rooms-and-add-ins.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

