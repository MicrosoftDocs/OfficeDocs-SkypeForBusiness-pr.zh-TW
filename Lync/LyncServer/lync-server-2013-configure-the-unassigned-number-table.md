---
title: Lync Server 2013：設定未指派號碼表
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
ms.openlocfilehash: 4c73027511ec8798010f1d22fb9bd19eeab27a7f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520250"
---
# <a name="configure-the-unassigned-number-table-in-lync-server-2013"></a><span data-ttu-id="400c0-102">在 Lync Server 2013 中設定未指派號碼表</span><span class="sxs-lookup"><span data-stu-id="400c0-102">Configure the unassigned number table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="400c0-103">_**主題上次修改日期：** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="400c0-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="400c0-104">在 [Lync Server 2013] 中，您可以指定對組織有效的電話號碼撥入電話號碼，但不會將其指派給使用者或電話。</span><span class="sxs-lookup"><span data-stu-id="400c0-104">In Lync Server 2013, you can specify what happens to incoming calls to phone numbers that are valid for your organization, but are not assigned to a user or phone.</span></span> <span data-ttu-id="400c0-105">來電者可能會聽到訊息，或可路由傳送至其他目的地，或兩者皆有。</span><span class="sxs-lookup"><span data-stu-id="400c0-105">Callers can hear a message, or can be routed to another destination, or both.</span></span>

<span data-ttu-id="400c0-106">設定未指派號碼表的方式取決於其使用方式。</span><span class="sxs-lookup"><span data-stu-id="400c0-106">How you configure the unassigned number table depends on how you want to use it.</span></span> <span data-ttu-id="400c0-107">您可以設定包含組織所有有效分機號碼、只包含未指派的分機號碼，或包含結合這兩種類型之號碼的表格。</span><span class="sxs-lookup"><span data-stu-id="400c0-107">You can configure the table with all the valid extensions for your organization, with only unassigned extensions, or with a combination of both types of numbers.</span></span> <span data-ttu-id="400c0-108">未指派號碼表可以同時包含已指派和未指派的號碼，但是只有在來電者撥打目前未指派的號碼時才會叫用。</span><span class="sxs-lookup"><span data-stu-id="400c0-108">The unassigned number table can include both assigned and unassigned numbers, but it is invoked only when a caller dials a number that is not currently assigned.</span></span> <span data-ttu-id="400c0-109">如果您在未指派號碼表中納入所有有效的分機號碼，可以指定每次某人離開組織時要執行的動作，而不必重新設定表格。</span><span class="sxs-lookup"><span data-stu-id="400c0-109">If you include all the valid extensions in the unassigned number table, you can specify the action that occurs whenever someone leaves your organization, without needing to reconfigure the table.</span></span> <span data-ttu-id="400c0-110">如果您在表格中包含未指派的副檔名，您可以修改針對特定數位所發生的動作。</span><span class="sxs-lookup"><span data-stu-id="400c0-110">If you include unassigned extensions in the table, you can modify the action that occurs for specific numbers.</span></span> <span data-ttu-id="400c0-111">例如，如果您變更客戶服務服務台的分機號碼，您可以在資料表中包含舊的客戶服務號碼，然後將其指派給提供新號碼的宣告。</span><span class="sxs-lookup"><span data-stu-id="400c0-111">For example, if you change the extension for your customer service desk, you can include the old customer service number in the table and then assign it to an announcement that provides the new number.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="400c0-112">在您設定未指派的號碼表之前，您的系統必須已定義宣告，或是已設定 Exchange 整合通訊 (UM) 自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="400c0-112">Before you configure the unassigned number table, your system must already either have Announcements defined or an Exchange Unified Messaging (UM) Auto Attendant set up.</span></span>



</div>

<div>


> [!TIP]  
> <span data-ttu-id="400c0-113">當某人呼叫未指派的號碼時，Lync Server 會從上到下搜尋未指派號碼表格，並使用第一個相符的範圍。</span><span class="sxs-lookup"><span data-stu-id="400c0-113">When someone calls an unassigned number, Lync Server searches the unassigned number table from top to bottom and uses the first matching range.</span></span> <span data-ttu-id="400c0-114">因此，應為表格中的最後一個範圍指定您想要執行做為最後一個手段的動作。</span><span class="sxs-lookup"><span data-stu-id="400c0-114">Therefore, an action that you want to be performed as a last resort should be specified for the last range in the table.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="400c0-115">本章節內容</span><span class="sxs-lookup"><span data-stu-id="400c0-115">In This Section</span></span>

<span data-ttu-id="400c0-116">[在 lync server 2013 中建立或修改未指派號碼範圍在](lync-server-2013-create-or-modify-an-unassigned-number-range.md) [lync server 中建立宣告 2013](lync-server-2013-create-an-announcement.md)</span><span class="sxs-lookup"><span data-stu-id="400c0-116">[Create or modify an unassigned number range in Lync Server 2013](lync-server-2013-create-or-modify-an-unassigned-number-range.md) [Create an announcement in Lync Server 2013](lync-server-2013-create-an-announcement.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

