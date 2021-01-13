---
title: 商務用 Skype Server 2015 中的 ClientVersions 表格
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
ms.assetid: 542316cf-a6db-4d52-ab28-8bf6d27a3b48
description: ClientVersions 表格是一種支援資料表，儲存資料庫中所記錄的工作階段之各種參與用戶端類型和版本清單。表格中的每筆記錄代表一個用戶端版本。
ms.openlocfilehash: 9f72a640fa294a51e483f496cad9913177dfcd2c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813313"
---
# <a name="clientversions-table-in-skype-for-business-server-2015"></a><span data-ttu-id="3414a-104">商務用 Skype Server 2015 中的 ClientVersions 表格</span><span class="sxs-lookup"><span data-stu-id="3414a-104">ClientVersions table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="3414a-p102">ClientVersions 表格是一種支援資料表，儲存資料庫中所記錄的工作階段之各種參與用戶端類型和版本清單。表格中的每筆記錄代表一個用戶端版本。</span><span class="sxs-lookup"><span data-stu-id="3414a-p102">The ClientVersions table is a supporting table that stores a list of the various client types and versions that have participated in sessions recorded in the database. Each record in the table represents one client version.</span></span>
  
|<span data-ttu-id="3414a-107">**欄**</span><span class="sxs-lookup"><span data-stu-id="3414a-107">**Column**</span></span>|<span data-ttu-id="3414a-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="3414a-108">**Data Type**</span></span>|<span data-ttu-id="3414a-109">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="3414a-109">**Key/Index**</span></span>|<span data-ttu-id="3414a-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="3414a-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3414a-111">**VersionId**</span><span class="sxs-lookup"><span data-stu-id="3414a-111">**VersionId**</span></span> <br/> |<span data-ttu-id="3414a-112">**int**</span><span class="sxs-lookup"><span data-stu-id="3414a-112">**int**</span></span> <br/> |<span data-ttu-id="3414a-113">主要</span><span class="sxs-lookup"><span data-stu-id="3414a-113">Primary</span></span>  <br/> |<span data-ttu-id="3414a-114">用於識別此用戶端類型及版本的唯一號碼。</span><span class="sxs-lookup"><span data-stu-id="3414a-114">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="3414a-115">**版本**</span><span class="sxs-lookup"><span data-stu-id="3414a-115">**Version**</span></span> <br/> |<span data-ttu-id="3414a-116">**Nvarchar (256)**</span><span class="sxs-lookup"><span data-stu-id="3414a-116">**nvarchar(256)**</span></span> <br/> ||<span data-ttu-id="3414a-117">版本名稱。</span><span class="sxs-lookup"><span data-stu-id="3414a-117">Version name.</span></span>  <br/> |
|<span data-ttu-id="3414a-118">**ClientType**</span><span class="sxs-lookup"><span data-stu-id="3414a-118">**ClientType**</span></span> <br/> |<span data-ttu-id="3414a-119">int</span><span class="sxs-lookup"><span data-stu-id="3414a-119">int</span></span>  <br/> ||<span data-ttu-id="3414a-120">指出工作階段所使用的用戶端類型。</span><span class="sxs-lookup"><span data-stu-id="3414a-120">Specifies the type of client used in the session.</span></span> <span data-ttu-id="3414a-121">如需詳細資訊，請參閱 [UserAgentDef 表格](useragentdef.md) 。</span><span class="sxs-lookup"><span data-stu-id="3414a-121">See the [UserAgentDef table](useragentdef.md) for more information.</span></span> <br/> <span data-ttu-id="3414a-122">此欄位是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="3414a-122">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

