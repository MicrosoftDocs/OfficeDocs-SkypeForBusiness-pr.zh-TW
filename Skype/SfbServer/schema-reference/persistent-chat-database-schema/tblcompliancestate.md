---
title: tblComplianceState
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
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState 包含集區範圍的相容性狀態資訊。
ms.openlocfilehash: 82c775b315976b0e5b112c476a41a8f5adc6a24c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809723"
---
# <a name="tblcompliancestate"></a><span data-ttu-id="76ca9-103">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="76ca9-103">tblComplianceState</span></span>
 
<span data-ttu-id="76ca9-104">tblComplianceState 包含集區範圍的相容性狀態資訊。</span><span class="sxs-lookup"><span data-stu-id="76ca9-104">tblComplianceState contains pool-wide compliance state information.</span></span>
  
<span data-ttu-id="76ca9-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="76ca9-105">**Columns**</span></span>

|<span data-ttu-id="76ca9-106">**欄**</span><span class="sxs-lookup"><span data-stu-id="76ca9-106">**Column**</span></span>|<span data-ttu-id="76ca9-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="76ca9-107">**Type**</span></span>|<span data-ttu-id="76ca9-108">**描述**</span><span class="sxs-lookup"><span data-stu-id="76ca9-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="76ca9-109">lastProcessedEntryID</span><span class="sxs-lookup"><span data-stu-id="76ca9-109">lastProcessedEntryID</span></span>  <br/> |<span data-ttu-id="76ca9-110">bigint，非 null</span><span class="sxs-lookup"><span data-stu-id="76ca9-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="76ca9-111">最新處理的相容性事件的識別碼。</span><span class="sxs-lookup"><span data-stu-id="76ca9-111">ID of the latest processed compliance event.</span></span>  <br/> |
|<span data-ttu-id="76ca9-112">activeServerID</span><span class="sxs-lookup"><span data-stu-id="76ca9-112">activeServerID</span></span>  <br/> |<span data-ttu-id="76ca9-113">int，非 null</span><span class="sxs-lookup"><span data-stu-id="76ca9-113">int, not null</span></span>  <br/> |<span data-ttu-id="76ca9-114">在資料庫上保留獨佔鎖定之規範伺服器的識別碼，如果沒有，則為-1。</span><span class="sxs-lookup"><span data-stu-id="76ca9-114">ID of the Compliance server holding the exclusive lock on the database, or -1 if none.</span></span>  <br/> |
|<span data-ttu-id="76ca9-115">lockExpirationTime</span><span class="sxs-lookup"><span data-stu-id="76ca9-115">lockExpirationTime</span></span>  <br/> |<span data-ttu-id="76ca9-116">datetime2，非 null</span><span class="sxs-lookup"><span data-stu-id="76ca9-116">datetime2, not null</span></span>  <br/> |<span data-ttu-id="76ca9-117">如果 activeServerID 不是-1) ，則鎖定到期時間 (。</span><span class="sxs-lookup"><span data-stu-id="76ca9-117">Lock expiration time (if activeServerID is not -1).</span></span>  <br/> |
   

