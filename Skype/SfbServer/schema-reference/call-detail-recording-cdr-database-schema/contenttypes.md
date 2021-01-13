---
title: 商務用 Skype Server 2015 中的 ContentTypes 表格
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
ms.assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
description: ContentTypes 表格是一種支援表格，可儲存點對點工作階段和會議會話中所使用的內容類型清單。 表格中的每一筆記錄代表一種內容類型。
ms.openlocfilehash: 461631c8fc824a23f0e4b22b65a3cbc8cf6a2c73
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816083"
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a><span data-ttu-id="f473d-104">商務用 Skype Server 2015 中的 ContentTypes 表格</span><span class="sxs-lookup"><span data-stu-id="f473d-104">ContentTypes table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="f473d-105">ContentTypes 表格是一種支援表格，可儲存點對點工作階段和會議會話中所使用的內容類型清單。</span><span class="sxs-lookup"><span data-stu-id="f473d-105">The ContentTypes table is a supporting table that stores a list of the content types used in both peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="f473d-106">表格中的每一筆記錄代表一種內容類型。</span><span class="sxs-lookup"><span data-stu-id="f473d-106">Each record in the table represents one content type.</span></span>
  
|<span data-ttu-id="f473d-107">**欄**</span><span class="sxs-lookup"><span data-stu-id="f473d-107">**Column**</span></span>|<span data-ttu-id="f473d-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="f473d-108">**Data Type**</span></span>|<span data-ttu-id="f473d-109">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="f473d-109">**Key/Index**</span></span>|<span data-ttu-id="f473d-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="f473d-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f473d-111">**ContentTypeId**</span><span class="sxs-lookup"><span data-stu-id="f473d-111">**ContentTypeId**</span></span> <br/> |<span data-ttu-id="f473d-112">int</span><span class="sxs-lookup"><span data-stu-id="f473d-112">int</span></span>  <br/> |<span data-ttu-id="f473d-113">主要</span><span class="sxs-lookup"><span data-stu-id="f473d-113">Primary</span></span>  <br/> |<span data-ttu-id="f473d-114">用於識別內容類型的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="f473d-114">Unique number identifying the content type.</span></span>  <br/> |
|<span data-ttu-id="f473d-115">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="f473d-115">**ContentType**</span></span> <br/> |<span data-ttu-id="f473d-116">Nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="f473d-116">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="f473d-117">內容類型名稱。</span><span class="sxs-lookup"><span data-stu-id="f473d-117">Content type name.</span></span>  <br/> |
   

