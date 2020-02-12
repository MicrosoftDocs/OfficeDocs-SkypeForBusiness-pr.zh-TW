---
title: 常設聊天室資料庫查詢範例
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 545b1a93-9758-4344-98cc-aa0e559d494f
description: 本節包含持久聊天資料庫的範例查詢。
ms.openlocfilehash: f161deb55cb9ecb0e42eb23e71cd842aa8f3d99a
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/11/2020
ms.locfileid: "41887712"
---
# <a name="sample-persistent-chat-database-queries"></a><span data-ttu-id="1ee95-103">常設聊天室資料庫查詢範例</span><span class="sxs-lookup"><span data-stu-id="1ee95-103">Sample Persistent Chat database queries</span></span>
 
<span data-ttu-id="1ee95-104">本節包含持久聊天資料庫的範例查詢。</span><span class="sxs-lookup"><span data-stu-id="1ee95-104">This section contains sample queries for the Persistent Chat database.</span></span>
  
<span data-ttu-id="1ee95-105">使用下列範例，在特定日期之後取得最活躍的持續聊天室清單。</span><span class="sxs-lookup"><span data-stu-id="1ee95-105">Use the following example to get a list of your most active Persistent Chat rooms after a certain date.</span></span>
  
```SQL
SELECT nodeName as ChatRoom, COUNT(*) as ChatMessages
  FROM tblChat, tblNode
  WHERE channelId = nodeID AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
  GROUP BY nodeName
  ORDER BY ChatMessages DESC
```

<span data-ttu-id="1ee95-106">使用下列範例，在特定日期之後取得最活躍的使用者清單。</span><span class="sxs-lookup"><span data-stu-id="1ee95-106">Use the following example to get a list of your most active users after a certain date.</span></span>
  
```SQL
SELECT prinName as Name, count(*) as ChatMessages
  FROM tblChat, tblPrincipal
  WHERE prinID = userId AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
  GROUP BY prinName
  ORDER BY ChatMessages DESC
```

<span data-ttu-id="1ee95-107">使用下列範例來取得曾經傳送「Hello World」郵件的所有人員清單。</span><span class="sxs-lookup"><span data-stu-id="1ee95-107">Use the following example to get a list of everyone who ever sent a message with "Hello World" in it.</span></span>
  
```SQL
SELECT nodeName as ChatRoom, prinName as Name, content as Message
  FROM tblChat, tblNode, tblPrincipal
  WHERE channelId = nodeID AND userId = prinID AND content like '%Hello World%'
```

<span data-ttu-id="1ee95-108">使用下列範例來取得特定主體的群組成員資格清單。</span><span class="sxs-lookup"><span data-stu-id="1ee95-108">Use the following example to get a list of group memberships for a certain principal.</span></span>
  
```SQL
SELECT prinName as Name    
  FROM tblPrincipalAffiliations as pa, tblPrincipal
  where principalID = 7 and affiliationID = prinID
```

<span data-ttu-id="1ee95-109">使用下列範例，取得使用者（Jane 道瓊）是直接成員的每個聊天室的清單。</span><span class="sxs-lookup"><span data-stu-id="1ee95-109">Use the following example to get a list of every chat room that a user, Jane Dow, is a direct member of.</span></span>
  
```SQL
SELECT DISTINCT nodeName as ChatRoom, prinName as Name          
  FROM tblPrincipalRole, tblPrincipal, tblNode
  WHERE  prinRoleNodeID = nodeID AND prinRolePrinID = prinID AND prinName = 'Jane Dow'
```

<span data-ttu-id="1ee95-110">使用下列範例來取得使用者已收到的邀請清單。</span><span class="sxs-lookup"><span data-stu-id="1ee95-110">Use the following example to get a list of invitations that a user has received.</span></span>
  
```SQL
SELECT prinName
      ,nodeName
      ,invID   
      ,createdOn
  FROM tblPrincipalInvites as inv, tblPrincipal as p, tblNode as n
  where inv.prinID = 5 AND inv.prinID = p.prinID and inv.nodeID = n.nodeID
  ORDER BY invID DESC
```
