---
title: Roles 表格
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: Roles 表格是一個靜態表格，用來儲存可能的會議角色（例如出席者和簡報者）的清單。
ms.openlocfilehash: 6c5e28ccd2d186b0122d70f91621a3365e6d2b07
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809973"
---
# <a name="roles-table"></a><span data-ttu-id="93c19-103">Roles 表格</span><span class="sxs-lookup"><span data-stu-id="93c19-103">Roles table</span></span>
 
<span data-ttu-id="93c19-104">Roles 表格是一個靜態表格，用來儲存可能的會議角色（例如出席者和簡報者）的清單。</span><span class="sxs-lookup"><span data-stu-id="93c19-104">The Roles table is a static table that stores the list of possible conference roles, such as attendee and presenter.</span></span>
  
|<span data-ttu-id="93c19-105">**欄**</span><span class="sxs-lookup"><span data-stu-id="93c19-105">**Column**</span></span>|<span data-ttu-id="93c19-106">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="93c19-106">**Data Type**</span></span>|<span data-ttu-id="93c19-107">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="93c19-107">**Key/Index**</span></span>|<span data-ttu-id="93c19-108">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="93c19-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="93c19-109">**RoleId**</span><span class="sxs-lookup"><span data-stu-id="93c19-109">**RoleId**</span></span> <br/> |<span data-ttu-id="93c19-110">Tinyint</span><span class="sxs-lookup"><span data-stu-id="93c19-110">tinyint</span></span>  <br/> |<span data-ttu-id="93c19-111">主要</span><span class="sxs-lookup"><span data-stu-id="93c19-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="93c19-112">**Role**</span><span class="sxs-lookup"><span data-stu-id="93c19-112">**Role**</span></span> <br/> |<span data-ttu-id="93c19-113">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="93c19-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="93c19-114">允許的值：</span><span class="sxs-lookup"><span data-stu-id="93c19-114">Allowed values:</span></span> <br/>  <span data-ttu-id="93c19-115">0 - 未知</span><span class="sxs-lookup"><span data-stu-id="93c19-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="93c19-116">1-簡報者</span><span class="sxs-lookup"><span data-stu-id="93c19-116">1 - Presenter</span></span> <br/>  <span data-ttu-id="93c19-117">2-出席者</span><span class="sxs-lookup"><span data-stu-id="93c19-117">2 - Attendee</span></span> <br/> |
   

