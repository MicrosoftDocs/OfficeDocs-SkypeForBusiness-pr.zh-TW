---
title: tblConfig
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig 包含部分持續聊天伺服器不支援的設定 (在單一列中)。
ms.openlocfilehash: 244eebcb88c67b521022f9d64888678f221d2369
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192744"
---
# <a name="tblconfig"></a><span data-ttu-id="cb300-103">tblConfig</span><span class="sxs-lookup"><span data-stu-id="cb300-103">tblConfig</span></span>
 
<span data-ttu-id="cb300-104">tblConfig 包含部分持續聊天伺服器不支援的設定 (在單一列中)。</span><span class="sxs-lookup"><span data-stu-id="cb300-104">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>
  
<span data-ttu-id="cb300-105">**分欄**</span><span class="sxs-lookup"><span data-stu-id="cb300-105">**Columns**</span></span>

|<span data-ttu-id="cb300-106">**左欄**</span><span class="sxs-lookup"><span data-stu-id="cb300-106">**Column**</span></span>|<span data-ttu-id="cb300-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="cb300-107">**Type**</span></span>|<span data-ttu-id="cb300-108">**說明**</span><span class="sxs-lookup"><span data-stu-id="cb300-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="cb300-109">configLabel</span><span class="sxs-lookup"><span data-stu-id="cb300-109">configLabel</span></span>  <br/> |<span data-ttu-id="cb300-110">Nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="cb300-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="cb300-111">包含 "pool"。</span><span class="sxs-lookup"><span data-stu-id="cb300-111">Contains "pool."</span></span>  <br/> |
|<span data-ttu-id="cb300-112">configContent</span><span class="sxs-lookup"><span data-stu-id="cb300-112">configContent</span></span>  <br/> |<span data-ttu-id="cb300-113">Nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="cb300-113">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="cb300-114">配置內容。</span><span class="sxs-lookup"><span data-stu-id="cb300-114">Configuration content.</span></span>  <br/> |
|<span data-ttu-id="cb300-115">configPoolID</span><span class="sxs-lookup"><span data-stu-id="cb300-115">configPoolID</span></span>  <br/> |<span data-ttu-id="cb300-116">GUID, 不是 null</span><span class="sxs-lookup"><span data-stu-id="cb300-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="cb300-117">資料庫實例的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="cb300-117">Unique ID of the database instance.</span></span>  <br/> |
   
<span data-ttu-id="cb300-118">**快速鍵**</span><span class="sxs-lookup"><span data-stu-id="cb300-118">**Key**</span></span>

|<span data-ttu-id="cb300-119">**左欄**</span><span class="sxs-lookup"><span data-stu-id="cb300-119">**Column**</span></span>|<span data-ttu-id="cb300-120">**說明**</span><span class="sxs-lookup"><span data-stu-id="cb300-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cb300-121">configLabel</span><span class="sxs-lookup"><span data-stu-id="cb300-121">configLabel</span></span>  <br/> |<span data-ttu-id="cb300-122">主鍵。</span><span class="sxs-lookup"><span data-stu-id="cb300-122">Primary key.</span></span>  <br/> |
   

