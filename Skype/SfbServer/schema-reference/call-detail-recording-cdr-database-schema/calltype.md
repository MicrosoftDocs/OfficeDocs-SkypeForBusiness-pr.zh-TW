---
title: 商務用 Skype Server 2015 中的 CallType 表格
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
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: CallType 表格是儲存可能通話類型清單的靜態表格。
ms.openlocfilehash: 89f29a2c826f4aef12cc0332e40df0fb421c3932
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813363"
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a><span data-ttu-id="3f245-103">商務用 Skype Server 2015 中的 CallType 表格</span><span class="sxs-lookup"><span data-stu-id="3f245-103">CallType table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="3f245-104">CallType 表格是儲存可能通話類型清單的靜態表格。</span><span class="sxs-lookup"><span data-stu-id="3f245-104">The CallType table is a static table that stores the list of possible call types.</span></span>
  
|<span data-ttu-id="3f245-105">**欄**</span><span class="sxs-lookup"><span data-stu-id="3f245-105">**Column**</span></span>|<span data-ttu-id="3f245-106">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="3f245-106">**Data Type**</span></span>|<span data-ttu-id="3f245-107">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="3f245-107">**Key/Index**</span></span>|<span data-ttu-id="3f245-108">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="3f245-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3f245-109">**CallTypeId**</span><span class="sxs-lookup"><span data-stu-id="3f245-109">**CallTypeId**</span></span> <br/> |<span data-ttu-id="3f245-110">int</span><span class="sxs-lookup"><span data-stu-id="3f245-110">int</span></span>  <br/> |<span data-ttu-id="3f245-111">主要</span><span class="sxs-lookup"><span data-stu-id="3f245-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="3f245-112">**CallType**</span><span class="sxs-lookup"><span data-stu-id="3f245-112">**CallType**</span></span> <br/> |<span data-ttu-id="3f245-113">Nvarchar</span><span class="sxs-lookup"><span data-stu-id="3f245-113">nvarchar</span></span>  <br/> || <span data-ttu-id="3f245-114">允許的值：</span><span class="sxs-lookup"><span data-stu-id="3f245-114">Allowed values:</span></span> <br/>  <span data-ttu-id="3f245-115">0 -- 不明</span><span class="sxs-lookup"><span data-stu-id="3f245-115">0 -- Unknown</span></span> <br/>  <span data-ttu-id="3f245-116">1-立即訊息</span><span class="sxs-lookup"><span data-stu-id="3f245-116">1 - Instant Messaging</span></span> <br/>  <span data-ttu-id="3f245-117">2--應用程式共用</span><span class="sxs-lookup"><span data-stu-id="3f245-117">2 -- Application Sharing</span></span> <br/>  <span data-ttu-id="3f245-118">3--音訊</span><span class="sxs-lookup"><span data-stu-id="3f245-118">3 -- Audio</span></span> <br/>  <span data-ttu-id="3f245-119">4-音訊和影片</span><span class="sxs-lookup"><span data-stu-id="3f245-119">4 - Audio and Video</span></span> <br/>  <span data-ttu-id="3f245-120">5-檔案傳輸</span><span class="sxs-lookup"><span data-stu-id="3f245-120">5 - File Transfer</span></span> <br/> |
   

