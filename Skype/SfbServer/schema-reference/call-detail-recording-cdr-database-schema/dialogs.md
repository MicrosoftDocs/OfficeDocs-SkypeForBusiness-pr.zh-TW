---
title: 商務用 Skype Server 2015 中的對話方塊表格
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
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: 對話方塊表格是一種支援資料表，可儲存點對點工作階段之 Dialogid 的相關資訊。
ms.openlocfilehash: a4f0bb8c63e165985ef09af8f9aafa071529bf1f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816043"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a><span data-ttu-id="012e2-103">商務用 Skype Server 2015 中的對話方塊表格</span><span class="sxs-lookup"><span data-stu-id="012e2-103">Dialogs table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="012e2-104">對話方塊表格是一種支援資料表，可儲存點對點工作階段之 Dialogid 的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="012e2-104">The Dialogs table is a supporting table that stores the information about DialogIDs for peer-to-peer sessions.</span></span>
  
|<span data-ttu-id="012e2-105">**欄**</span><span class="sxs-lookup"><span data-stu-id="012e2-105">**Column**</span></span>|<span data-ttu-id="012e2-106">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="012e2-106">**Data Type**</span></span>|<span data-ttu-id="012e2-107">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="012e2-107">**Key/Index**</span></span>|<span data-ttu-id="012e2-108">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="012e2-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="012e2-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="012e2-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="012e2-110">datetime</span><span class="sxs-lookup"><span data-stu-id="012e2-110">datetime</span></span>  <br/> |<span data-ttu-id="012e2-111">主要</span><span class="sxs-lookup"><span data-stu-id="012e2-111">Primary</span></span>  <br/> |<span data-ttu-id="012e2-112">會話要求的時間;與 SessionIDSeq 搭配使用，以唯一識別會話。</span><span class="sxs-lookup"><span data-stu-id="012e2-112">Time of session request; used in conjunction with SessionIDSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="012e2-113">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="012e2-113">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="012e2-114">int</span><span class="sxs-lookup"><span data-stu-id="012e2-114">int</span></span>  <br/> |<span data-ttu-id="012e2-115">主要</span><span class="sxs-lookup"><span data-stu-id="012e2-115">Primary</span></span>  <br/> |<span data-ttu-id="012e2-116">識別工作階段的 ID 號碼。</span><span class="sxs-lookup"><span data-stu-id="012e2-116">ID number to identify the session.</span></span> <span data-ttu-id="012e2-117">與 SessionIDTime 搭配使用，以唯一識別會話。</span><span class="sxs-lookup"><span data-stu-id="012e2-117">Used in conjunction with SessionIDTime to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="012e2-118">**ExternalChecksum**</span><span class="sxs-lookup"><span data-stu-id="012e2-118">**ExternalChecksum**</span></span> <br/> |<span data-ttu-id="012e2-119">int</span><span class="sxs-lookup"><span data-stu-id="012e2-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="012e2-120">ExternalID 的校驗和。</span><span class="sxs-lookup"><span data-stu-id="012e2-120">Checksum of the ExternalID.</span></span> <span data-ttu-id="012e2-121">此欄位是用來增加資料庫搜尋的速度。</span><span class="sxs-lookup"><span data-stu-id="012e2-121">This field is used to increase the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="012e2-122">**ExternalId**</span><span class="sxs-lookup"><span data-stu-id="012e2-122">**ExternalId**</span></span> <br/> |<span data-ttu-id="012e2-123">Varbinary (775) </span><span class="sxs-lookup"><span data-stu-id="012e2-123">varbinary(775)</span></span>  <br/> | <br/> |<span data-ttu-id="012e2-124">以二進位儲存的 SIP 對話方塊識別碼。</span><span class="sxs-lookup"><span data-stu-id="012e2-124">SIP dialog ID, stored as a binary.</span></span> <span data-ttu-id="012e2-125">二進位檔案的格式為：</span><span class="sxs-lookup"><span data-stu-id="012e2-125">The format of the binary is:</span></span>  <br/> <span data-ttu-id="012e2-126">dialog; 從-標籤; to-標記</span><span class="sxs-lookup"><span data-stu-id="012e2-126">dialog;from-tag;to-tag</span></span>  <br/> <span data-ttu-id="012e2-127">您可以使用下列語法將此資料轉換成文字格式：</span><span class="sxs-lookup"><span data-stu-id="012e2-127">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

