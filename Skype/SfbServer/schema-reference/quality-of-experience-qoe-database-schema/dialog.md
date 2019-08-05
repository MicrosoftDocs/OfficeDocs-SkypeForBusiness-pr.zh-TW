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
localization_priority: Normal
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: 對話方塊表格是支援資料表;每個記錄代表一個 [會話初始通訊協定 (SIP)] 對話方塊。
ms.openlocfilehash: e6bbaa3c40ebf53c5fd9fc410acca7779128bf39
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192676"
---
# <a name="dialog-table"></a><span data-ttu-id="e77b4-103">Dialog 表格</span><span class="sxs-lookup"><span data-stu-id="e77b4-103">Dialog table</span></span>
 
<span data-ttu-id="e77b4-104">對話方塊表格是支援資料表;每個記錄代表一個 [會話初始通訊協定 (SIP)] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="e77b4-104">The Dialog table is a supporting table; each record represents one Session Initiation Protocol (SIP) dialog.</span></span>
  
|<span data-ttu-id="e77b4-105">**左欄**</span><span class="sxs-lookup"><span data-stu-id="e77b4-105">**Column**</span></span>|<span data-ttu-id="e77b4-106">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="e77b4-106">**Data Type**</span></span>|<span data-ttu-id="e77b4-107">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="e77b4-107">**Key/Index**</span></span>|<span data-ttu-id="e77b4-108">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="e77b4-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e77b4-109">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="e77b4-109">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="e77b4-110">datetime</span><span class="sxs-lookup"><span data-stu-id="e77b4-110">datetime</span></span>  <br/> |<span data-ttu-id="e77b4-111">首選</span><span class="sxs-lookup"><span data-stu-id="e77b4-111">Primary</span></span>  <br/> |<span data-ttu-id="e77b4-112">優質 (QoE) 代理程式從來電者或被叫方接收到第一個報告的時間。</span><span class="sxs-lookup"><span data-stu-id="e77b4-112">Time when the Quality of Excellence (QoE) agent receives the first report from either caller or callee.</span></span> <span data-ttu-id="e77b4-113">與 SessionSeq 搭配使用, 可唯一識別會話。</span><span class="sxs-lookup"><span data-stu-id="e77b4-113">Used in conjunction with SessionSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="e77b4-114">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="e77b4-114">**SessionSeq**</span></span> <br/> |<span data-ttu-id="e77b4-115">int</span><span class="sxs-lookup"><span data-stu-id="e77b4-115">int</span></span>  <br/> |<span data-ttu-id="e77b4-116">首選</span><span class="sxs-lookup"><span data-stu-id="e77b4-116">Primary</span></span>  <br/> |<span data-ttu-id="e77b4-117">[順序編號] 可在有相同 ConferenceDateTime 的情況下區分會話。</span><span class="sxs-lookup"><span data-stu-id="e77b4-117">Sequence number to differentiate sessions when they have the same ConferenceDateTime.</span></span>  <br/> |
|<span data-ttu-id="e77b4-118">**DialogID**</span><span class="sxs-lookup"><span data-stu-id="e77b4-118">**DialogID**</span></span> <br/> |<span data-ttu-id="e77b4-119">Varchar (256)</span><span class="sxs-lookup"><span data-stu-id="e77b4-119">varchar(256)</span></span>  <br/> ||<span data-ttu-id="e77b4-120">全域唯一的對話方塊識別碼。</span><span class="sxs-lookup"><span data-stu-id="e77b4-120">Dialog ID which is globally unique.</span></span>  <br/> |
|<span data-ttu-id="e77b4-121">**DialogIDChecksum**</span><span class="sxs-lookup"><span data-stu-id="e77b4-121">**DialogIDChecksum**</span></span> <br/> |<span data-ttu-id="e77b4-122">int</span><span class="sxs-lookup"><span data-stu-id="e77b4-122">int</span></span>  <br/> |<span data-ttu-id="e77b4-123">index</span><span class="sxs-lookup"><span data-stu-id="e77b4-123">index</span></span>  <br/> |<span data-ttu-id="e77b4-124">對話方塊識別碼的校驗和。</span><span class="sxs-lookup"><span data-stu-id="e77b4-124">Checksum of the Dialog ID.</span></span>  <br/> |
   

