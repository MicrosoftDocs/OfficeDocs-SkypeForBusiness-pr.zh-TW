---
title: '[IPAddress] 表格'
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
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: '[IPAddress] 表格會將 IP 位址對應至 [經驗] 資料庫中其他位置使用的唯一 IP 位址識別碼。 此表格是在 Microsoft Lync Server 2013 中推出。'
ms.openlocfilehash: 2789d436b007a5208d98a4b32dca14517fbaaa57
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41809541"
---
# <a name="ipaddress-table"></a><span data-ttu-id="d5d5d-104">[IPAddress] 表格</span><span class="sxs-lookup"><span data-stu-id="d5d5d-104">IPAddress table</span></span>
 
<span data-ttu-id="d5d5d-105">[IPAddress] 表格會將 IP 位址對應至 [經驗] 資料庫中其他位置使用的唯一 IP 位址識別碼。</span><span class="sxs-lookup"><span data-stu-id="d5d5d-105">The IPAddress table maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="d5d5d-106">此表格是在 Microsoft Lync Server 2013 中推出。</span><span class="sxs-lookup"><span data-stu-id="d5d5d-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="d5d5d-107">**左欄**</span><span class="sxs-lookup"><span data-stu-id="d5d5d-107">**Column**</span></span>|<span data-ttu-id="d5d5d-108">**資料類型**</span><span class="sxs-lookup"><span data-stu-id="d5d5d-108">**Data Type**</span></span>|<span data-ttu-id="d5d5d-109">**索引鍵/索引**</span><span class="sxs-lookup"><span data-stu-id="d5d5d-109">**Key/Index**</span></span>|<span data-ttu-id="d5d5d-110">**詳細資料**</span><span class="sxs-lookup"><span data-stu-id="d5d5d-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d5d5d-111">**IPAddressKey**</span><span class="sxs-lookup"><span data-stu-id="d5d5d-111">**IPAddressKey**</span></span> <br/> |<span data-ttu-id="d5d5d-112">int</span><span class="sxs-lookup"><span data-stu-id="d5d5d-112">int</span></span>  <br/> |<span data-ttu-id="d5d5d-113">首選</span><span class="sxs-lookup"><span data-stu-id="d5d5d-113">Primary</span></span>  <br/> |<span data-ttu-id="d5d5d-114">指定 IP 位址的唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="d5d5d-114">Unique identifier for the specified IP address.</span></span>  <br/> |
|<span data-ttu-id="d5d5d-115">**IPAddress**</span><span class="sxs-lookup"><span data-stu-id="d5d5d-115">**IPAddress**</span></span> <br/> |<span data-ttu-id="d5d5d-116">Varchar （50）</span><span class="sxs-lookup"><span data-stu-id="d5d5d-116">varchar(50)</span></span>  <br/> |<span data-ttu-id="d5d5d-117">唯一</span><span class="sxs-lookup"><span data-stu-id="d5d5d-117">Unique</span></span>  <br/> |<span data-ttu-id="d5d5d-118">對應至 IpAddressKey 的唯一 IP 位址（例如，189.168.1.1）。</span><span class="sxs-lookup"><span data-stu-id="d5d5d-118">Unique IP address (for example, 189.168.1.1) that maps to the IpAddressKey.</span></span> <span data-ttu-id="d5d5d-119">這可能是 IPv4 或 IPv6 位址。</span><span class="sxs-lookup"><span data-stu-id="d5d5d-119">This may be either an IPv4 or an IPv6 address.</span></span>  <br/> |
   

