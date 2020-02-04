---
title: Lync Server 2013：與 Microsoft Exchange Server 2013 整合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Integrating Lync Server 2013 and Exchange Server 2013
ms:assetid: 795dc1c6-524f-4012-8b66-103b55198044
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688098(v=OCS.15)
ms:contentKeyID: 49733697
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1467f6a570f83908eb5809f9493303bdc91c169
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725853"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="integrating-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a><span data-ttu-id="caf89-102">整合 Microsoft Lync Server 2013 與 Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="caf89-102">Integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="caf89-103">_**主題上次修改日期：** 2014-07-09_</span><span class="sxs-lookup"><span data-stu-id="caf89-103">_**Topic Last Modified:** 2014-07-09_</span></span>

<span data-ttu-id="caf89-104">Exchange 和 Lync Server 的整合與相容性較長。</span><span class="sxs-lookup"><span data-stu-id="caf89-104">Exchange and Lync Server have a long history of integration and compatibility.</span></span> <span data-ttu-id="caf89-105">這個整合在各自的用戶端應用程式中最明顯。</span><span class="sxs-lookup"><span data-stu-id="caf89-105">This integration is most noticeable within their respective client application.</span></span> <span data-ttu-id="caf89-106">例如，您可以在 Microsoft Outlook 中報告 Lync 目前狀態資訊。同樣地，Lync 可以使用 Outlook 行事歷來自動更新該目前狀態資訊。</span><span class="sxs-lookup"><span data-stu-id="caf89-106">For example, Lync presence information can be reported in Microsoft Outlook; likewise, Lync can use Outlook calendar to automatically update that presence information.</span></span> <span data-ttu-id="caf89-107">（例如，Lync 可隨時將您的狀態變更為 [忙碌]，行事曆會顯示您已排程會議。）雖然您不需要執行 Exchange，就能執行 Lync Server （或反之），不過您不一定要使用這兩個產品一起 epitomizes [更好地配合] 的定義。</span><span class="sxs-lookup"><span data-stu-id="caf89-107">(For example, Lync can change your status to Busy any time your calendar shows that you have a meeting scheduled.) Although you do not have to run Exchange in order to run Lync Server (or vice-versa) there's little doubt that using the two products together epitomizes the very definition of the term "better together."</span></span>

<span data-ttu-id="caf89-108">在 Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013 的發行中，尤其如此。</span><span class="sxs-lookup"><span data-stu-id="caf89-108">This is especially true with the release of Microsoft Lync Server 2013 and Microsoft Exchange Server 2013.</span></span> <span data-ttu-id="caf89-109">除了 Microsoft Exchange Server 2010 和 Microsoft Lync Server 2010 中的 [整合郵件] 和 [IM 與目前狀態] 等功能之外，伺服器產品的2013版本都包含許多新功能。</span><span class="sxs-lookup"><span data-stu-id="caf89-109">In addition to features, such as unified messaging and IM and presence, that are found in Microsoft Exchange Server 2010 and Microsoft Lync Server 2010, the 2013 releases of the server products include a number of new capabilities.</span></span> <span data-ttu-id="caf89-110">這些功能包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="caf89-110">These capabilities include such things as:</span></span>

  - <span data-ttu-id="caf89-111">**Lync 存檔整合**。</span><span class="sxs-lookup"><span data-stu-id="caf89-111">**Lync Archiving Integration**.</span></span> <span data-ttu-id="caf89-112">在 Lync Server 2013 中，系統管理員仍能選擇將即時消息和網路會議記錄存檔至 SQL Server （與在 Lync Server 2010 中歸檔這些記錄的方式相同）。</span><span class="sxs-lookup"><span data-stu-id="caf89-112">In Lync Server 2013 administrators still have the option of having instant messaging and Web conferencing transcripts archived to SQL Server (the same way these transcripts were archived in Lync Server 2010).</span></span> <span data-ttu-id="caf89-113">或者，管理員可以選擇將記錄歸檔至 Exchange 2013，將這些記錄儲存在個別的使用者信箱中，就像 Exchange 存檔通訊一樣。</span><span class="sxs-lookup"><span data-stu-id="caf89-113">Alternatively, however, administrators can choose to have transcripts archived to Exchange 2013, storing those transcripts in the individual user mailboxes in the same way in which Exchange archives communications.</span></span> <span data-ttu-id="caf89-114">這代表所有電子通訊的單一儲備庫（來自 Exchange 和 Lync Server），可讓您更輕鬆地搜尋及取回那些已歸檔的通訊（如果需要）。</span><span class="sxs-lookup"><span data-stu-id="caf89-114">That means a single repository for all your electronic communications (from both Exchange and Lync Server), which makes it much easier to search for and retrieve those archived communications should the need arise.</span></span>

  - <span data-ttu-id="caf89-115">**整合連絡人存放區**。</span><span class="sxs-lookup"><span data-stu-id="caf89-115">**Unified Contact Store**.</span></span> <span data-ttu-id="caf89-116">在 Lync Server 2010 中，使用者必須在 Outlook 和 Lync 中維護獨立的連絡人清單;事實上，若要確保您在兩種產品中都能使用相同的連絡人，您必須維護重複的連絡人清單，一個適用于 Outlook，另一個適用于 Lync。</span><span class="sxs-lookup"><span data-stu-id="caf89-116">In Lync Server 2010, users had to maintain separate contact lists in Outlook and Lync; in fact, to ensure that you had the same contacts available in both products you had to maintain duplicate contact lists, one for Outlook and one for Lync.</span></span> <span data-ttu-id="caf89-117">不過，您可以使用 Lync Server 2013，將使用者連絡人儲存在 Exchange 2013 和整合連絡人存放區中。</span><span class="sxs-lookup"><span data-stu-id="caf89-117">With Lync Server 2013, however, user contacts can be stored in Exchange 2013 and the unified contact store.</span></span> <span data-ttu-id="caf89-118">使用單一連絡人存放區可以讓使用者只保留一組連絡人，並在 Lync 2013、Outlook 2013 和 Outlook Web Access 2013 中提供相同的連絡人集合。</span><span class="sxs-lookup"><span data-stu-id="caf89-118">Using a single contact store enables users to maintain just one set of contacts, with that same set of contacts being available in Lync 2013, Outlook 2013, and Outlook Web Access 2013.</span></span>

  - <span data-ttu-id="caf89-119">**從 OWA 進行 Lync 會議排程**。</span><span class="sxs-lookup"><span data-stu-id="caf89-119">**Lync Meeting Scheduling from OWA**.</span></span> <span data-ttu-id="caf89-120">透過 Lync Server 2013 與 Exchange 2013 整合，使用者可以從 Outlook Web Access 2013 排程 Lync 會議。</span><span class="sxs-lookup"><span data-stu-id="caf89-120">With Lync Server 2013 and Exchange 2013 integration, users can schedule Lync meetings from Outlook Web Access 2013.</span></span>

  - <span data-ttu-id="caf89-121">**高解析度相片**。</span><span class="sxs-lookup"><span data-stu-id="caf89-121">**High resolution photos**.</span></span> <span data-ttu-id="caf89-122">Lync 2010 只能顯示較小的連絡人相片，這是因為這些相片是儲存在 Active Directory 中，而 Active Directory 在儲存的相片上以48圖元大小限制的方式來強加48圖元。</span><span class="sxs-lookup"><span data-stu-id="caf89-122">Lync 2010 could only display small photos of your contacts; that's because those photos were stored in Active Directory, and Active Directory imposes a 48 pixel by 48 pixel size limitation on stored photos.</span></span> <span data-ttu-id="caf89-123">不過，有了 Lync Server 2013，相片可以儲存在 Microsoft Exchange 中;這可讓高解析度相片的大小為648圖元乘648圖元。</span><span class="sxs-lookup"><span data-stu-id="caf89-123">With Lync Server 2013, however, photos can be stored in Microsoft Exchange; that allows for high-resolution photos as large as 648 pixels by 648 pixels.</span></span> <span data-ttu-id="caf89-124">您可能會想到，Lync 2013 已升級為允許顯示這些高解析度相片。</span><span class="sxs-lookup"><span data-stu-id="caf89-124">As you might expect, Lync 2013 has been upgraded to allow for the display of these high-resolution photographs.</span></span>

<span data-ttu-id="caf89-125">請記住，這些新功能需要同時使用 Lync Server 2013 和 Exchange 2013。</span><span class="sxs-lookup"><span data-stu-id="caf89-125">Keep in mind that these new features require the use of both Lync Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="caf89-126">此外，想要充分利用這些新功能的使用者，都必須在 Lync Server 2013 和 Exchange 2013 上擁有帳戶，且必須使用最新版本的用戶端軟體（例如 Lync 2013）。</span><span class="sxs-lookup"><span data-stu-id="caf89-126">In addition to that, users who hope to take full advantage of these new capabilities must have accounts on Lync Server 2013 and Exchange 2013, and must be using the latest versions of the client software (e.g., Lync 2013).</span></span> <span data-ttu-id="caf89-127">例如，已在 Lync Server 2010 上託管的使用者無法使用「整合連絡人存放區」;同樣地，在 Lync 2010 中無法顯示高解析度相片。</span><span class="sxs-lookup"><span data-stu-id="caf89-127">For example, the unified contact store is not available to users who have been homed on Lync Server 2010; likewise, high-resolution photos cannot be displayed in Lync 2010.</span></span>

<span data-ttu-id="caf89-128">本檔提供集成 Lync Server 2013 與 Exchange 2013 的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="caf89-128">This documentation provides information on integrating Lync Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="caf89-129">包括啟用新功能（例如，歸檔整合與整合連絡人存放區）的逐步資訊。</span><span class="sxs-lookup"><span data-stu-id="caf89-129">including step-by-step information on enabling new features such archiving Integration and the unified contact store.</span></span> <span data-ttu-id="caf89-130">本檔中的內容不會討論這兩個產品的初始設定和配置。</span><span class="sxs-lookup"><span data-stu-id="caf89-130">What this documentation does not do is discuss the initial setup and configuration of these two products.</span></span> <span data-ttu-id="caf89-131">如需有關部署 Lync Server 2013 的詳細資訊，請參閱 Lync Server [http://go.microsoft.com/fwlink/p/?LinkId=246127](http://go.microsoft.com/fwlink/p/?linkid=246127)2013 技術中心（位於）。</span><span class="sxs-lookup"><span data-stu-id="caf89-131">For details about deploying Lync Server 2013 see the Lync Server 2013 Tech Center at [http://go.microsoft.com/fwlink/p/?LinkId=246127](http://go.microsoft.com/fwlink/p/?linkid=246127).</span></span> <span data-ttu-id="caf89-132">如需有關部署 Exchange 2013 的詳細資訊，請參閱 Exchange [http://go.microsoft.com/fwlink/p/?LinkId=268528](http://go.microsoft.com/fwlink/p/?linkid=268528)2013 技術中心。</span><span class="sxs-lookup"><span data-stu-id="caf89-132">For details about deploying Exchange 2013 see the Exchange 2013 Tech Center at [http://go.microsoft.com/fwlink/p/?LinkId=268528](http://go.microsoft.com/fwlink/p/?linkid=268528).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="caf89-133">本節內容</span><span class="sxs-lookup"><span data-stu-id="caf89-133">In This Section</span></span>

[<span data-ttu-id="caf89-134">整合 Microsoft Lync Server 2013 與 Microsoft Exchange Server 2013 的先決條件</span><span class="sxs-lookup"><span data-stu-id="caf89-134">Prerequisites for integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>](lync-server-2013-prerequisites-for-integrating-with-exchange-server-2013.md)

[<span data-ttu-id="caf89-135">在 Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013 中設定合作夥伴應用程式</span><span class="sxs-lookup"><span data-stu-id="caf89-135">Configuring partner applications in Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>](lync-server-2013-configuring-partner-applications-in-lync-server-2013-and-exchange-server-2013.md)

[<span data-ttu-id="caf89-136">將 Microsoft Lync Server 2013 設定為使用 Microsoft Exchange Server 2013 歸檔</span><span class="sxs-lookup"><span data-stu-id="caf89-136">Configuring Microsoft Lync Server 2013 to use Microsoft Exchange Server 2013 archiving</span></span>](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md)

[<span data-ttu-id="caf89-137">設定 Microsoft SharePoint Server 2013 以搜尋已歸檔的 Microsoft Lync Server 2013 資料</span><span class="sxs-lookup"><span data-stu-id="caf89-137">Configuring Microsoft SharePoint Server 2013 to search for archived Microsoft Lync Server 2013 data</span></span>](lync-server-2013-configuring-microsoft-sharepoint-server-2013-to-search-for-archived-lync-server-2013-data.md)

[<span data-ttu-id="caf89-138">將 Microsoft Lync Server 2013 設定為使用整合連絡人存放區</span><span class="sxs-lookup"><span data-stu-id="caf89-138">Configuring Microsoft Lync Server 2013 to use the unified contact store</span></span>](lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md)

[<span data-ttu-id="caf89-139">在 Microsoft Lync Server 2013 中設定高解析度相片的使用</span><span class="sxs-lookup"><span data-stu-id="caf89-139">Configuring the use of high-resolution photos in Microsoft Lync Server 2013</span></span>](lync-server-2013-configuring-the-use-of-high-resolution-photos.md)

[<span data-ttu-id="caf89-140">針對 Microsoft Lync Server 2013 語音信箱設定 Microsoft Exchange Server 2013 整合通訊</span><span class="sxs-lookup"><span data-stu-id="caf89-140">Configuring Microsoft Exchange Server 2013 Unified Messaging for Microsoft Lync Server 2013 voice mail</span></span>](lync-server-2013-configuring-microsoft-exchange-server-2013-unified-messaging-for-lync-server-2013-voice-mail.md)

[<span data-ttu-id="caf89-141">整合 Microsoft Lync Server 2013 與 Microsoft Outlook Web App 2013</span><span class="sxs-lookup"><span data-stu-id="caf89-141">Integrating Microsoft Lync Server 2013 and Microsoft Outlook Web App 2013</span></span>](lync-server-2013-integrating-lync-server-and-outlook-web-app-2013.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

