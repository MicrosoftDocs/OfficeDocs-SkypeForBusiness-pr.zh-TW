---
title: 常設聊天室伺服器最佳做法
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
ms.openlocfilehash: 119bc67622928ec2e60f082e72322e7b0b923c2e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743673"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="persistent-chat-server-best-practices"></a>常設聊天室伺服器最佳做法

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-06_

當您建立類別和持續聊天室並設計您的範圍與成員資格時，下列秘訣可協助您規劃：

  - 如果您的公司不需要具道德的牆，請不要縮小類別樹狀結構中的範圍。 將所有使用者放在單一類別的範圍內，並建立該類別中的所有聊天室。 接著，只使用成員資格清單來准許或限制每個聊天室的存取權。

  - 在大多數情況下，您應該讓使用者建立新的聊天室，讓您可以隨時開始討論新主題。 您可以將**製作者**清單製作成與**AllowedMembers**清單相同的方式來執行此動作。 不過，如果您想要只允許中央支援小組或指定的使用者建立會議室，請將**製作者**清單設為適當的子集。

  - 為每個聊天室提供完整的名稱和描述摘要，說明其在您的組織中要符合的位置。 因為使用者使用聊天室時看不到類別名稱，所以您無法依賴類別名稱來協助使用者判斷聊天室的預期論壇。

  - 如果您有特定的命名慣例或其他存取控制或驗證實現，您可能會想要建立自訂的聊天室建立工作流程。 [持續聊天] 設定可讓您自訂**RoomManagementUrl**給您所裝載的內容。 例如，當使用者按一下 Lync 用戶端中**的 [建立聊天室**] 時，可以將它們重新導向至您的自訂方案。

  - 您可以透過在聊天室中加入其他商務資料，來建立各種增益集，協助改善聊天室的體驗。 系統管理員必須註冊他們想要在系統中允許的增益集。 聊天室管理員與創意者可以從允許的增益集清單中選擇與其各自的聊天室最相關的增益集。

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中管理類別、聊天室及增益集](lync-server-2013-managing-categories-rooms-and-add-ins.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

