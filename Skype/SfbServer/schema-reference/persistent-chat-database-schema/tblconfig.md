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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig 包含部分持續聊天伺服器不支援的設定（在單一列中）。
ms.openlocfilehash: f79af00d6a9f97f0ce0836684a284779be662c1d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814621"
---
# <a name="tblconfig"></a><span data-ttu-id="ae234-103">tblConfig</span><span class="sxs-lookup"><span data-stu-id="ae234-103">tblConfig</span></span>
 
<span data-ttu-id="ae234-104">tblConfig 包含部分持續聊天伺服器不支援的設定（在單一列中）。</span><span class="sxs-lookup"><span data-stu-id="ae234-104">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>
  
<span data-ttu-id="ae234-105">**分欄**</span><span class="sxs-lookup"><span data-stu-id="ae234-105">**Columns**</span></span>

|<span data-ttu-id="ae234-106">**左欄**</span><span class="sxs-lookup"><span data-stu-id="ae234-106">**Column**</span></span>|<span data-ttu-id="ae234-107">**類型**</span><span class="sxs-lookup"><span data-stu-id="ae234-107">**Type**</span></span>|<span data-ttu-id="ae234-108">**說明**</span><span class="sxs-lookup"><span data-stu-id="ae234-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ae234-109">configLabel</span><span class="sxs-lookup"><span data-stu-id="ae234-109">configLabel</span></span>  <br/> |<span data-ttu-id="ae234-110">Nvarchar （255），not null</span><span class="sxs-lookup"><span data-stu-id="ae234-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="ae234-111">包含 "pool"。</span><span class="sxs-lookup"><span data-stu-id="ae234-111">Contains "pool."</span></span>  <br/> |
|<span data-ttu-id="ae234-112">configContent</span><span class="sxs-lookup"><span data-stu-id="ae234-112">configContent</span></span>  <br/> |<span data-ttu-id="ae234-113">Nvarchar （max）</span><span class="sxs-lookup"><span data-stu-id="ae234-113">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="ae234-114">配置內容。</span><span class="sxs-lookup"><span data-stu-id="ae234-114">Configuration content.</span></span>  <br/> |
|<span data-ttu-id="ae234-115">configPoolID</span><span class="sxs-lookup"><span data-stu-id="ae234-115">configPoolID</span></span>  <br/> |<span data-ttu-id="ae234-116">GUID，不是 null</span><span class="sxs-lookup"><span data-stu-id="ae234-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="ae234-117">資料庫實例的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="ae234-117">Unique ID of the database instance.</span></span>  <br/> |
   
<span data-ttu-id="ae234-118">**機碼**</span><span class="sxs-lookup"><span data-stu-id="ae234-118">**Key**</span></span>

|<span data-ttu-id="ae234-119">**左欄**</span><span class="sxs-lookup"><span data-stu-id="ae234-119">**Column**</span></span>|<span data-ttu-id="ae234-120">**說明**</span><span class="sxs-lookup"><span data-stu-id="ae234-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ae234-121">configLabel</span><span class="sxs-lookup"><span data-stu-id="ae234-121">configLabel</span></span>  <br/> |<span data-ttu-id="ae234-122">主鍵。</span><span class="sxs-lookup"><span data-stu-id="ae234-122">Primary key.</span></span>  <br/> |
   

