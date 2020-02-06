---
title: 商務用 Skype Server 2015 中的對話方塊表格
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
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: 對話方塊表格是一個支援資料表，可儲存點對點工作階段之 DialogIDs 的相關資訊。
ms.openlocfilehash: f6cfc3e078ee8f4492d6f5baf65f66df77d7aedf
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815271"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a><span data-ttu-id="df2bd-103">商務用 Skype Server 2015 中的對話方塊表格</span><span class="sxs-lookup"><span data-stu-id="df2bd-103">Dialogs table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="df2bd-104">對話方塊表格是一個支援資料表，可儲存點對點工作階段之 DialogIDs 的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="df2bd-104">The Dialogs table is a supporting table that stores the information about DialogIDs for peer-to-peer sessions.</span></span>
  
|<span data-ttu-id="df2bd-105">**左欄**</span><span class="sxs-lookup"><span data-stu-id="df2bd-105">**Column**</span></span>|<span data-ttu-id="df2bd-106">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="df2bd-106">**Data Type**</span></span>|<span data-ttu-id="df2bd-107">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="df2bd-107">**Key/Index**</span></span>|<span data-ttu-id="df2bd-108">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="df2bd-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="df2bd-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="df2bd-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="df2bd-110">datetime</span><span class="sxs-lookup"><span data-stu-id="df2bd-110">datetime</span></span>  <br/> |<span data-ttu-id="df2bd-111">首選</span><span class="sxs-lookup"><span data-stu-id="df2bd-111">Primary</span></span>  <br/> |<span data-ttu-id="df2bd-112">會話要求的時間;與 SessionIDSeq 搭配使用，可唯一識別會話。</span><span class="sxs-lookup"><span data-stu-id="df2bd-112">Time of session request; used in conjunction with SessionIDSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="df2bd-113">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="df2bd-113">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="df2bd-114">int</span><span class="sxs-lookup"><span data-stu-id="df2bd-114">int</span></span>  <br/> |<span data-ttu-id="df2bd-115">首選</span><span class="sxs-lookup"><span data-stu-id="df2bd-115">Primary</span></span>  <br/> |<span data-ttu-id="df2bd-116">識別會話的識別碼編號。</span><span class="sxs-lookup"><span data-stu-id="df2bd-116">ID number to identify the session.</span></span> <span data-ttu-id="df2bd-117">與 SessionIDTime 搭配使用，可唯一識別會話。</span><span class="sxs-lookup"><span data-stu-id="df2bd-117">Used in conjunction with SessionIDTime to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="df2bd-118">**ExternalChecksum**</span><span class="sxs-lookup"><span data-stu-id="df2bd-118">**ExternalChecksum**</span></span> <br/> |<span data-ttu-id="df2bd-119">int</span><span class="sxs-lookup"><span data-stu-id="df2bd-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="df2bd-120">ExternalID 的校驗和。</span><span class="sxs-lookup"><span data-stu-id="df2bd-120">Checksum of the ExternalID.</span></span> <span data-ttu-id="df2bd-121">此欄位可用來提高資料庫搜尋的速度。</span><span class="sxs-lookup"><span data-stu-id="df2bd-121">This field is used to increase the speed of database searches.</span></span>  <br/> |
|<span data-ttu-id="df2bd-122">**ExternalId**</span><span class="sxs-lookup"><span data-stu-id="df2bd-122">**ExternalId**</span></span> <br/> |<span data-ttu-id="df2bd-123">Varbinary （775）</span><span class="sxs-lookup"><span data-stu-id="df2bd-123">varbinary(775)</span></span>  <br/> | <br/> |<span data-ttu-id="df2bd-124">SIP 對話方塊識別碼，儲存為二進位。</span><span class="sxs-lookup"><span data-stu-id="df2bd-124">SIP dialog ID, stored as a binary.</span></span> <span data-ttu-id="df2bd-125">二進位檔案的格式為：</span><span class="sxs-lookup"><span data-stu-id="df2bd-125">The format of the binary is:</span></span>  <br/> <span data-ttu-id="df2bd-126">對話方塊; 從標籤; 到標籤</span><span class="sxs-lookup"><span data-stu-id="df2bd-126">dialog;from-tag;to-tag</span></span>  <br/> <span data-ttu-id="df2bd-127">您可以使用下列語法，將此資料轉換成文字格式：</span><span class="sxs-lookup"><span data-stu-id="df2bd-127">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

