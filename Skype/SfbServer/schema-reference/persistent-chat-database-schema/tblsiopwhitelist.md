---
title: tblSiopWhiteList
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
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: tblSiopWhiteList 是可與節點相關聯的已註冊增益集清單。
ms.openlocfilehash: ae287a1a32b09ce309c688dac2a042913383a263
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812111"
---
# <a name="tblsiopwhitelist"></a><span data-ttu-id="5258b-103">tblSiopWhiteList</span><span class="sxs-lookup"><span data-stu-id="5258b-103">tblSiopWhiteList</span></span>
 
<span data-ttu-id="5258b-104">tblSiopWhiteList 是可與節點相關聯的已註冊增益集清單。</span><span class="sxs-lookup"><span data-stu-id="5258b-104">tblSiopWhiteList is the list of registered add-ins that can be associated with nodes.</span></span>
  
<span data-ttu-id="5258b-105">**分欄**</span><span class="sxs-lookup"><span data-stu-id="5258b-105">**Columns**</span></span>

|<span data-ttu-id="5258b-106">**左欄**</span><span class="sxs-lookup"><span data-stu-id="5258b-106">**Column**</span></span>|<span data-ttu-id="5258b-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="5258b-107">**Type**</span></span>|<span data-ttu-id="5258b-108">**說明**</span><span class="sxs-lookup"><span data-stu-id="5258b-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5258b-109">siopID</span><span class="sxs-lookup"><span data-stu-id="5258b-109">siopID</span></span>  <br/> |<span data-ttu-id="5258b-110">GUID，不是 null</span><span class="sxs-lookup"><span data-stu-id="5258b-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="5258b-111">增益集的 GUID。</span><span class="sxs-lookup"><span data-stu-id="5258b-111">GUID of the add-in.</span></span>  <br/> |
|<span data-ttu-id="5258b-112">siopName</span><span class="sxs-lookup"><span data-stu-id="5258b-112">siopName</span></span>  <br/> |<span data-ttu-id="5258b-113">Nvarchar （50），not null</span><span class="sxs-lookup"><span data-stu-id="5258b-113">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="5258b-114">顯示-增益集的名稱。</span><span class="sxs-lookup"><span data-stu-id="5258b-114">Display-name of the add-in.</span></span>  <br/> |
|<span data-ttu-id="5258b-115">siopUrl</span><span class="sxs-lookup"><span data-stu-id="5258b-115">siopUrl</span></span>  <br/> |<span data-ttu-id="5258b-116">Nvarchar （255），not null</span><span class="sxs-lookup"><span data-stu-id="5258b-116">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="5258b-117">增益集的 URL。</span><span class="sxs-lookup"><span data-stu-id="5258b-117">URL of the add-in.</span></span>  <br/> |
   
<span data-ttu-id="5258b-118">**機碼**</span><span class="sxs-lookup"><span data-stu-id="5258b-118">**Key**</span></span>

|<span data-ttu-id="5258b-119">**左欄**</span><span class="sxs-lookup"><span data-stu-id="5258b-119">**Column**</span></span>|<span data-ttu-id="5258b-120">**說明**</span><span class="sxs-lookup"><span data-stu-id="5258b-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5258b-121">siopID</span><span class="sxs-lookup"><span data-stu-id="5258b-121">siopID</span></span>  <br/> |<span data-ttu-id="5258b-122">主鍵。</span><span class="sxs-lookup"><span data-stu-id="5258b-122">Primary key.</span></span>  <br/> |
   

