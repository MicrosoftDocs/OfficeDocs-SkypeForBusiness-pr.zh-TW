---
title: Dialog 表格
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: Dialog 表格是一種支援資料表；每筆記錄代表一個工作階段初始通訊協定 (SIP) 對話方塊。
ms.openlocfilehash: 05d9519c9aef20b8c82d904a9d5718a4de8c092c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815843"
---
# <a name="dialog-table"></a><span data-ttu-id="6366d-103">Dialog 表格</span><span class="sxs-lookup"><span data-stu-id="6366d-103">Dialog table</span></span>
 
<span data-ttu-id="6366d-104">Dialog 表格是一種支援資料表；每筆記錄代表一個工作階段初始通訊協定 (SIP) 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="6366d-104">The Dialog table is a supporting table; each record represents one Session Initiation Protocol (SIP) dialog.</span></span>
  
|<span data-ttu-id="6366d-105">**欄**</span><span class="sxs-lookup"><span data-stu-id="6366d-105">**Column**</span></span>|<span data-ttu-id="6366d-106">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="6366d-106">**Data Type**</span></span>|<span data-ttu-id="6366d-107">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="6366d-107">**Key/Index**</span></span>|<span data-ttu-id="6366d-108">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="6366d-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6366d-109">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="6366d-109">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="6366d-110">datetime</span><span class="sxs-lookup"><span data-stu-id="6366d-110">datetime</span></span>  <br/> |<span data-ttu-id="6366d-111">主要</span><span class="sxs-lookup"><span data-stu-id="6366d-111">Primary</span></span>  <br/> |<span data-ttu-id="6366d-p101">卓越品質 (Quality of Excellence, QoE) 代理程式從發話者或受話者收到第一份報告的時間。其會與 SessionSeq 搭配使用，專門用於識別工作階段。</span><span class="sxs-lookup"><span data-stu-id="6366d-p101">Time when the Quality of Excellence (QoE) agent receives the first report from either caller or callee. Used in conjunction with SessionSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="6366d-114">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="6366d-114">**SessionSeq**</span></span> <br/> |<span data-ttu-id="6366d-115">int</span><span class="sxs-lookup"><span data-stu-id="6366d-115">int</span></span>  <br/> |<span data-ttu-id="6366d-116">主要</span><span class="sxs-lookup"><span data-stu-id="6366d-116">Primary</span></span>  <br/> |<span data-ttu-id="6366d-117">當工作階段的 ConferenceDateTime 相同時，用來區分工作階段的序號。</span><span class="sxs-lookup"><span data-stu-id="6366d-117">Sequence number to differentiate sessions when they have the same ConferenceDateTime.</span></span>  <br/> |
|<span data-ttu-id="6366d-118">**DialogID**</span><span class="sxs-lookup"><span data-stu-id="6366d-118">**DialogID**</span></span> <br/> |<span data-ttu-id="6366d-119">Varchar (256) </span><span class="sxs-lookup"><span data-stu-id="6366d-119">varchar(256)</span></span>  <br/> ||<span data-ttu-id="6366d-120">全域唯一的對話方塊 ID。</span><span class="sxs-lookup"><span data-stu-id="6366d-120">Dialog ID which is globally unique.</span></span>  <br/> |
|<span data-ttu-id="6366d-121">**DialogIDChecksum**</span><span class="sxs-lookup"><span data-stu-id="6366d-121">**DialogIDChecksum**</span></span> <br/> |<span data-ttu-id="6366d-122">int</span><span class="sxs-lookup"><span data-stu-id="6366d-122">int</span></span>  <br/> |<span data-ttu-id="6366d-123">index</span><span class="sxs-lookup"><span data-stu-id="6366d-123">index</span></span>  <br/> |<span data-ttu-id="6366d-124">對話方塊 ID 的總和檢查碼。</span><span class="sxs-lookup"><span data-stu-id="6366d-124">Checksum of the Dialog ID.</span></span>  <br/> |
   

