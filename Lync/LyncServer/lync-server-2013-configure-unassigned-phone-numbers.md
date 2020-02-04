---
title: Lync Server 2013：設定未指派的電話號碼
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure unassigned phone numbers
ms:assetid: a0650659-dce7-455f-8977-02454bbfa400
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182559(v=OCS.15)
ms:contentKeyID: 48185009
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02dd4f71b3bc9d53fcbd65f4e143fec550c6a528
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736463"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-unassigned-phone-numbers-in-lync-server-2013"></a><span data-ttu-id="cc29d-102">在 Lync Server 2013 中設定未指派的電話號碼</span><span class="sxs-lookup"><span data-stu-id="cc29d-102">Configure unassigned phone numbers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc29d-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="cc29d-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="cc29d-104">Lync Server 可讓您設定對您的組織有效且未獲指派給使用者或電話的電話號碼撥入電話的行為。</span><span class="sxs-lookup"><span data-stu-id="cc29d-104">Lync Server lets you configure what happens to incoming calls to phone numbers that are valid for your organization, but are not assigned to a user or a phone.</span></span> <span data-ttu-id="cc29d-105">若要設定此類通話的處理方式，您必須設定未指派的 [數位] 資料表。</span><span class="sxs-lookup"><span data-stu-id="cc29d-105">To configure the handling of such calls, you set up an unassigned number table.</span></span> <span data-ttu-id="cc29d-106">您可以使用表格，將呼叫路由至宣告應用程式或 Exchange UM 伺服器。</span><span class="sxs-lookup"><span data-stu-id="cc29d-106">You can use the table to route the calls to an Announcement application or to an Exchange UM server.</span></span>

<span data-ttu-id="cc29d-p102">設定未指派號碼表的方式取決於其使用方式。您可以設定包含組織所有有效分機號碼、只包含未指派的分機號碼，或包含結合這兩種類型之號碼的表格。未指派號碼表可以同時包含已指派和未指派的號碼，但是只有在來電者撥打目前未指派的號碼時才會叫用。如果您在未指派號碼表中納入所有有效的分機號碼，可以指定每次某人離開組織時要執行的動作，而不必重新設定表格。如果表格中包含未指派的分機號碼，您可以針對特定號碼設計要採取的動作。例如，如果您變更客服人員的分機號碼，則可以在表格中包含舊的客服號碼，並且將它指派給提供新號碼的宣告。</span><span class="sxs-lookup"><span data-stu-id="cc29d-p102">How you configure the unassigned number table depends on how you want to use it. You can configure the table with all the valid extensions for your organization, with only unassigned extensions, or with a combination of both types of numbers. The unassigned number table can include both assigned and unassigned numbers, but it is invoked only when a caller dials a number that is not currently assigned. If you include all the valid extensions in the unassigned number table, you can specify the action that occurs whenever someone leaves your organization, without needing to reconfigure the table. If you include unassigned extensions in the table, you can tailor the action that occurs for specific numbers. For example, if you change the extension for your customer service desk, you can include the old customer service number in the table and assign it to an announcement that provides the new number.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="cc29d-113">在您設定 [未指定的數位] 資料表之前，您必須已定義一個或多個宣告，或已設定 Exchange UM 自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="cc29d-113">Before you configure the unassigned number table, you must already have either one or more announcements defined or an Exchange UM Auto Attendant set up.</span></span> <span data-ttu-id="cc29d-114">如需建立宣告的詳細資訊，請參閱<A href="lync-server-2013-create-an-announcement.md">在 Lync Server 2013 中建立公告</A>。</span><span class="sxs-lookup"><span data-stu-id="cc29d-114">For details about creating announcements, see <A href="lync-server-2013-create-an-announcement.md">Create an announcement in Lync Server 2013</A>.</span></span> <span data-ttu-id="cc29d-115">若要查看您是否已設定 Exchange UM 設定，請執行<STRONG>CsExUmContact</STRONG> Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="cc29d-115">To see if you have configured Exchange UM settings, run the <STRONG>Get-CsExUmContact</STRONG> cmdlet.</span></span> <span data-ttu-id="cc29d-116">如需詳細資訊，請參閱<A href="https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact">CsExUmContact</A>。</span><span class="sxs-lookup"><span data-stu-id="cc29d-116">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsExUmContact">Get-CsExUmContact</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="cc29d-117">本節內容</span><span class="sxs-lookup"><span data-stu-id="cc29d-117">In This Section</span></span>

  - [<span data-ttu-id="cc29d-118">在 Lync Server 2013 中建立或修改未指定的數位範圍</span><span class="sxs-lookup"><span data-stu-id="cc29d-118">Create or modify an unassigned number range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-unassigned-number-range.md)

  - [<span data-ttu-id="cc29d-119">在 Lync Server 2013 中刪除未指定的數位範圍</span><span class="sxs-lookup"><span data-stu-id="cc29d-119">Delete an unassigned number range in Lync Server 2013</span></span>](lync-server-2013-delete-an-unassigned-number-range.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

