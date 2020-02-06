---
title: 商務用 Skype Server 2015 中的 ClientVersions 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: ClientVersions 資料表是一個支援資料表，可儲存已參與在資料庫中記錄的會話的各種用戶端類型和版本清單。 資料表中的每一筆記錄代表一個用戶端版本。
ms.openlocfilehash: c616f7d44d138732e96f2d71c7fdf0197c75ca5c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815401"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a><span data-ttu-id="a27ee-104">商務用 Skype Server 2015 中的 ClientVersions 表格</span><span class="sxs-lookup"><span data-stu-id="a27ee-104">ClientVersions table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a27ee-105">ClientVersions 資料表是一個支援資料表，可儲存已參與在資料庫中記錄的會話的各種用戶端類型和版本清單。</span><span class="sxs-lookup"><span data-stu-id="a27ee-105">The ClientVersions table is a supporting table that stores a list of the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="a27ee-106">資料表中的每一筆記錄代表一個用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="a27ee-106">Each record in the table represents one client version.</span></span>
  
|<span data-ttu-id="a27ee-107">**左欄**</span><span class="sxs-lookup"><span data-stu-id="a27ee-107">**Column**</span></span>|<span data-ttu-id="a27ee-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="a27ee-108">**Data Type**</span></span>|<span data-ttu-id="a27ee-109">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="a27ee-109">**Key/Index**</span></span>|<span data-ttu-id="a27ee-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="a27ee-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a27ee-111">**VersionId**</span><span class="sxs-lookup"><span data-stu-id="a27ee-111">**VersionId**</span></span> <br/> |<span data-ttu-id="a27ee-112">**int**</span><span class="sxs-lookup"><span data-stu-id="a27ee-112">**int**</span></span> <br/> |<span data-ttu-id="a27ee-113">首選</span><span class="sxs-lookup"><span data-stu-id="a27ee-113">Primary</span></span>  <br/> |<span data-ttu-id="a27ee-114">標識此用戶端類型與版本的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="a27ee-114">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="a27ee-115">**版本**</span><span class="sxs-lookup"><span data-stu-id="a27ee-115">**Version**</span></span> <br/> |<span data-ttu-id="a27ee-116">**Nvarchar （256）**</span><span class="sxs-lookup"><span data-stu-id="a27ee-116">**nvarchar(256)**</span></span> <br/> ||<span data-ttu-id="a27ee-117">版本名稱。</span><span class="sxs-lookup"><span data-stu-id="a27ee-117">Version name.</span></span>  <br/> |
|<span data-ttu-id="a27ee-118">**ClientType**</span><span class="sxs-lookup"><span data-stu-id="a27ee-118">**ClientType**</span></span> <br/> |<span data-ttu-id="a27ee-119">int</span><span class="sxs-lookup"><span data-stu-id="a27ee-119">int</span></span>  <br/> ||<span data-ttu-id="a27ee-120">指定會話中使用的用戶端類型。</span><span class="sxs-lookup"><span data-stu-id="a27ee-120">Specifies the type of client used in the session.</span></span> <span data-ttu-id="a27ee-121">如需詳細資訊，請參閱[UserAgentDef 資料表](useragentdef.md)。</span><span class="sxs-lookup"><span data-stu-id="a27ee-121">See the [UserAgentDef table](useragentdef.md) for more information.</span></span> <br/> <span data-ttu-id="a27ee-122">此欄位是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="a27ee-122">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

