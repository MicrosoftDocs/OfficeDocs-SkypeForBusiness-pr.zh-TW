---
title: Lync Server 2013： 設定未指派號碼表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the unassigned number table
ms:assetid: eaa01986-e92f-4328-acf6-4e46c4306a04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399053(v=OCS.15)
ms:contentKeyID: 48185908
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ceb3aa60273439c94a5d936efe826e77dcc683be
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043195"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-unassigned-number-table-in-lync-server-2013"></a><span data-ttu-id="0a906-102">在 Lync Server 2013 中設定未指派號碼表</span><span class="sxs-lookup"><span data-stu-id="0a906-102">Configure the unassigned number table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0a906-103">_**主題上次修改日期：** 2012年-10-30_</span><span class="sxs-lookup"><span data-stu-id="0a906-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="0a906-104">在 Lync Server 2013 中，您可以指定至適用於您的組織，但不是會指派給使用者或電話的電話號碼的傳入呼叫會發生什麼事。</span><span class="sxs-lookup"><span data-stu-id="0a906-104">In Lync Server 2013, you can specify what happens to incoming calls to phone numbers that are valid for your organization, but are not assigned to a user or phone.</span></span> <span data-ttu-id="0a906-105">來電者可以聽到訊息，或可以路由傳送到其他目的地，或兩者。</span><span class="sxs-lookup"><span data-stu-id="0a906-105">Callers can hear a message, or can be routed to another destination, or both.</span></span>

<span data-ttu-id="0a906-106">設定未指派號碼表的方式取決於其使用方式。</span><span class="sxs-lookup"><span data-stu-id="0a906-106">How you configure the unassigned number table depends on how you want to use it.</span></span> <span data-ttu-id="0a906-107">您可以設定包含組織所有有效分機號碼、只包含未指派的分機號碼，或包含結合這兩種類型之號碼的表格。</span><span class="sxs-lookup"><span data-stu-id="0a906-107">You can configure the table with all the valid extensions for your organization, with only unassigned extensions, or with a combination of both types of numbers.</span></span> <span data-ttu-id="0a906-108">未指派號碼表可以同時包含已指派和未指派的號碼，但是只有在來電者撥打目前未指派的號碼時才會叫用。</span><span class="sxs-lookup"><span data-stu-id="0a906-108">The unassigned number table can include both assigned and unassigned numbers, but it is invoked only when a caller dials a number that is not currently assigned.</span></span> <span data-ttu-id="0a906-109">如果您在未指派號碼表中納入所有有效的分機號碼，可以指定每次某人離開組織時要執行的動作，而不必重新設定表格。</span><span class="sxs-lookup"><span data-stu-id="0a906-109">If you include all the valid extensions in the unassigned number table, you can specify the action that occurs whenever someone leaves your organization, without needing to reconfigure the table.</span></span> <span data-ttu-id="0a906-110">如果您在表格中包含未指派的擴充功能，您可以修改的週期定期發生特定的數字的巨集指令。</span><span class="sxs-lookup"><span data-stu-id="0a906-110">If you include unassigned extensions in the table, you can modify the action that occurs for specific numbers.</span></span> <span data-ttu-id="0a906-111">例如，如果您變更分機的客戶服務台人員時，您可以在表格中包含舊的客戶健保號碼，並再將其指派給提供新的數字的宣告。</span><span class="sxs-lookup"><span data-stu-id="0a906-111">For example, if you change the extension for your customer service desk, you can include the old customer service number in the table and then assign it to an announcement that provides the new number.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0a906-112">設定未指派號碼表之前，您的系統必須已定義宣告或設定 Exchange 整合通訊 (UM) 自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="0a906-112">Before you configure the unassigned number table, your system must already either have Announcements defined or an Exchange Unified Messaging (UM) Auto Attendant set up.</span></span>



</div>

<div>


> [!TIP]  
> <span data-ttu-id="0a906-113">如果某人撥打未指派的號碼，Lync Server 會搜尋從上到下未指派號碼表，並使用第一個比對範圍。</span><span class="sxs-lookup"><span data-stu-id="0a906-113">When someone calls an unassigned number, Lync Server searches the unassigned number table from top to bottom and uses the first matching range.</span></span> <span data-ttu-id="0a906-114">因此，應為表格中的最後一個範圍指定您想要做為最後的手段執行巨集指令。</span><span class="sxs-lookup"><span data-stu-id="0a906-114">Therefore, an action that you want to be performed as a last resort should be specified for the last range in the table.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0a906-115">本章節內容</span><span class="sxs-lookup"><span data-stu-id="0a906-115">In This Section</span></span>

<span data-ttu-id="0a906-116">[建立或修改 Lync Server 2013 中的未指派號碼範圍](lync-server-2013-create-or-modify-an-unassigned-number-range.md)[建立 Lync Server 2013 中的宣告](lync-server-2013-create-an-announcement.md)</span><span class="sxs-lookup"><span data-stu-id="0a906-116">[Create or modify an unassigned number range in Lync Server 2013](lync-server-2013-create-or-modify-an-unassigned-number-range.md) [Create an announcement in Lync Server 2013](lync-server-2013-create-an-announcement.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

