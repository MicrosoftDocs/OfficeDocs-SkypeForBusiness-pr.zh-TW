---
title: Dialog 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: 對話方塊表格是支援資料表;每個記錄代表一個 [會話初始通訊協定（SIP）] 對話方塊。
ms.openlocfilehash: 85d4a9f16a88db386565c065161eedeb61fba913
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41809531"
---
# <a name="dialog-table"></a><span data-ttu-id="3ba3e-103">Dialog 表格</span><span class="sxs-lookup"><span data-stu-id="3ba3e-103">Dialog table</span></span>
 
<span data-ttu-id="3ba3e-104">對話方塊表格是支援資料表;每個記錄代表一個 [會話初始通訊協定（SIP）] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="3ba3e-104">The Dialog table is a supporting table; each record represents one Session Initiation Protocol (SIP) dialog.</span></span>
  
|<span data-ttu-id="3ba3e-105">**左欄**</span><span class="sxs-lookup"><span data-stu-id="3ba3e-105">**Column**</span></span>|<span data-ttu-id="3ba3e-106">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="3ba3e-106">**Data Type**</span></span>|<span data-ttu-id="3ba3e-107">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="3ba3e-107">**Key/Index**</span></span>|<span data-ttu-id="3ba3e-108">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="3ba3e-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3ba3e-109">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="3ba3e-109">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="3ba3e-110">datetime</span><span class="sxs-lookup"><span data-stu-id="3ba3e-110">datetime</span></span>  <br/> |<span data-ttu-id="3ba3e-111">首選</span><span class="sxs-lookup"><span data-stu-id="3ba3e-111">Primary</span></span>  <br/> |<span data-ttu-id="3ba3e-112">優質（QoE）代理程式從來電者或被叫方接收到第一個報告的時間。</span><span class="sxs-lookup"><span data-stu-id="3ba3e-112">Time when the Quality of Excellence (QoE) agent receives the first report from either caller or callee.</span></span> <span data-ttu-id="3ba3e-113">與 SessionSeq 搭配使用，可唯一識別會話。</span><span class="sxs-lookup"><span data-stu-id="3ba3e-113">Used in conjunction with SessionSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="3ba3e-114">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="3ba3e-114">**SessionSeq**</span></span> <br/> |<span data-ttu-id="3ba3e-115">int</span><span class="sxs-lookup"><span data-stu-id="3ba3e-115">int</span></span>  <br/> |<span data-ttu-id="3ba3e-116">首選</span><span class="sxs-lookup"><span data-stu-id="3ba3e-116">Primary</span></span>  <br/> |<span data-ttu-id="3ba3e-117">[順序編號] 可在有相同 ConferenceDateTime 的情況下區分會話。</span><span class="sxs-lookup"><span data-stu-id="3ba3e-117">Sequence number to differentiate sessions when they have the same ConferenceDateTime.</span></span>  <br/> |
|<span data-ttu-id="3ba3e-118">**DialogID**</span><span class="sxs-lookup"><span data-stu-id="3ba3e-118">**DialogID**</span></span> <br/> |<span data-ttu-id="3ba3e-119">Varchar （256）</span><span class="sxs-lookup"><span data-stu-id="3ba3e-119">varchar(256)</span></span>  <br/> ||<span data-ttu-id="3ba3e-120">全域唯一的對話方塊識別碼。</span><span class="sxs-lookup"><span data-stu-id="3ba3e-120">Dialog ID which is globally unique.</span></span>  <br/> |
|<span data-ttu-id="3ba3e-121">**DialogIDChecksum**</span><span class="sxs-lookup"><span data-stu-id="3ba3e-121">**DialogIDChecksum**</span></span> <br/> |<span data-ttu-id="3ba3e-122">int</span><span class="sxs-lookup"><span data-stu-id="3ba3e-122">int</span></span>  <br/> |<span data-ttu-id="3ba3e-123">index</span><span class="sxs-lookup"><span data-stu-id="3ba3e-123">index</span></span>  <br/> |<span data-ttu-id="3ba3e-124">對話方塊識別碼的校驗和。</span><span class="sxs-lookup"><span data-stu-id="3ba3e-124">Checksum of the Dialog ID.</span></span>  <br/> |
   

