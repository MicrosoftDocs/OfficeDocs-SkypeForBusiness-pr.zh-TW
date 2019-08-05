---
title: Roles 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: Roles 資料表是一個靜態表格, 可儲存出席者與簡報者等可能的會議角色清單。
ms.openlocfilehash: 2cf1fb22230d92951df0b3b8e18a5bd666c73519
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192802"
---
# <a name="roles-table"></a><span data-ttu-id="b034a-103">Roles 表格</span><span class="sxs-lookup"><span data-stu-id="b034a-103">Roles table</span></span>
 
<span data-ttu-id="b034a-104">Roles 資料表是一個靜態表格, 可儲存出席者與簡報者等可能的會議角色清單。</span><span class="sxs-lookup"><span data-stu-id="b034a-104">The Roles table is a static table that stores the list of possible conference roles, such as attendee and presenter.</span></span>
  
|<span data-ttu-id="b034a-105">**左欄**</span><span class="sxs-lookup"><span data-stu-id="b034a-105">**Column**</span></span>|<span data-ttu-id="b034a-106">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="b034a-106">**Data Type**</span></span>|<span data-ttu-id="b034a-107">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="b034a-107">**Key/Index**</span></span>|<span data-ttu-id="b034a-108">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="b034a-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b034a-109">**RoleId**</span><span class="sxs-lookup"><span data-stu-id="b034a-109">**RoleId**</span></span> <br/> |<span data-ttu-id="b034a-110">Tinyint</span><span class="sxs-lookup"><span data-stu-id="b034a-110">tinyint</span></span>  <br/> |<span data-ttu-id="b034a-111">首選</span><span class="sxs-lookup"><span data-stu-id="b034a-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="b034a-112">**角色**</span><span class="sxs-lookup"><span data-stu-id="b034a-112">**Role**</span></span> <br/> |<span data-ttu-id="b034a-113">Nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b034a-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="b034a-114">允許的值:</span><span class="sxs-lookup"><span data-stu-id="b034a-114">Allowed values:</span></span> <br/>  <span data-ttu-id="b034a-115">0-未知</span><span class="sxs-lookup"><span data-stu-id="b034a-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="b034a-116">1-簡報者</span><span class="sxs-lookup"><span data-stu-id="b034a-116">1 - Presenter</span></span> <br/>  <span data-ttu-id="b034a-117">2-出席者</span><span class="sxs-lookup"><span data-stu-id="b034a-117">2 - Attendee</span></span> <br/> |
   

