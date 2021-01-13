---
title: 範例常設聊天室資料庫查詢
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 545b1a93-9758-4344-98cc-aa0e559d494f
description: 本節包含 Persistent Chat 資料庫的範例查詢。
ms.openlocfilehash: 74cb6c1029cdeaabcd74a34898731b44c71f05a7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823103"
---
# <a name="sample-persistent-chat-database-queries"></a><span data-ttu-id="568be-103">範例常設聊天室資料庫查詢</span><span class="sxs-lookup"><span data-stu-id="568be-103">Sample Persistent Chat database queries</span></span>
 
<span data-ttu-id="568be-104">本節包含 Persistent Chat 資料庫的範例查詢。</span><span class="sxs-lookup"><span data-stu-id="568be-104">This section contains sample queries for the Persistent Chat database.</span></span>
  
<span data-ttu-id="568be-105">使用下列範例來取得特定日期之後最活躍的持久聊天室清單。</span><span class="sxs-lookup"><span data-stu-id="568be-105">Use the following example to get a list of your most active Persistent Chat rooms after a certain date.</span></span>
  
```SQL
SELECT nodeName as ChatRoom, COUNT(*) as ChatMessages
  FROM tblChat, tblNode
  WHERE channelId = nodeID AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
  GROUP BY nodeName
  ORDER BY ChatMessages DESC
```

<span data-ttu-id="568be-106">請使用下列範例來取得特定日期之後最活躍的使用者清單。</span><span class="sxs-lookup"><span data-stu-id="568be-106">Use the following example to get a list of your most active users after a certain date.</span></span>
  
```SQL
SELECT prinName as Name, count(*) as ChatMessages
  FROM tblChat, tblPrincipal
  WHERE prinID = userId AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
  GROUP BY prinName
  ORDER BY ChatMessages DESC
```

<span data-ttu-id="568be-107">請使用下列範例來取得曾傳送內含 “Hello World” 之訊息的所有人清單。</span><span class="sxs-lookup"><span data-stu-id="568be-107">Use the following example to get a list of everyone who ever sent a message with "Hello World" in it.</span></span>
  
```SQL
SELECT nodeName as ChatRoom, prinName as Name, content as Message
  FROM tblChat, tblNode, tblPrincipal
  WHERE channelId = nodeID AND userId = prinID AND content like '%Hello World%'
```

<span data-ttu-id="568be-108">請使用下列範例來取得特定主體的群組成員資格清單。</span><span class="sxs-lookup"><span data-stu-id="568be-108">Use the following example to get a list of group memberships for a certain principal.</span></span>
  
```SQL
SELECT prinName as Name    
  FROM tblPrincipalAffiliations as pa, tblPrincipal
  where principalID = 7 and affiliationID = prinID
```

<span data-ttu-id="568be-109">請使用下列範例來取得使用者 Jane Dow 為直接成員的每個聊天室清單。</span><span class="sxs-lookup"><span data-stu-id="568be-109">Use the following example to get a list of every chat room that a user, Jane Dow, is a direct member of.</span></span>
  
```SQL
SELECT DISTINCT nodeName as ChatRoom, prinName as Name          
  FROM tblPrincipalRole, tblPrincipal, tblNode
  WHERE  prinRoleNodeID = nodeID AND prinRolePrinID = prinID AND prinName = 'Jane Dow'
```

<span data-ttu-id="568be-110">請使用下列範例來取得使用者已收到的邀請清單。</span><span class="sxs-lookup"><span data-stu-id="568be-110">Use the following example to get a list of invitations that a user has received.</span></span>
  
```SQL
SELECT prinName
      ,nodeName
      ,invID   
      ,createdOn
  FROM tblPrincipalInvites as inv, tblPrincipal as p, tblNode as n
  where inv.prinID = 5 AND inv.prinID = p.prinID and inv.nodeID = n.nodeID
  ORDER BY invID DESC
```
