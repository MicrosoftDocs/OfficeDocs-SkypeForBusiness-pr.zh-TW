---
title: 'Microsoft Exchange Server 2013 與整合 Lync Server 2013:'
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
ms.openlocfilehash: c1c60768311f4fbf832f3dbe2ac4a0c2e8e55298
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145392"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="integrating-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a><span data-ttu-id="1863d-102">整合 Microsoft Lync Server 2013 與 Microsoft Exchange Server 2013</span><span class="sxs-lookup"><span data-stu-id="1863d-102">Integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1863d-103">_**上次修改主題：** 2014年-07-09_</span><span class="sxs-lookup"><span data-stu-id="1863d-103">_**Topic Last Modified:** 2014-07-09_</span></span>

<span data-ttu-id="1863d-104">Exchange 和 Lync Server 具有整合和相容性的長歷程記錄。</span><span class="sxs-lookup"><span data-stu-id="1863d-104">Exchange and Lync Server have a long history of integration and compatibility.</span></span> <span data-ttu-id="1863d-105">這項整合是最明顯其各自的用戶端應用程式內。</span><span class="sxs-lookup"><span data-stu-id="1863d-105">This integration is most noticeable within their respective client application.</span></span> <span data-ttu-id="1863d-106">例如，在 Microsoft Outlook 中報告 Lync 目前狀態資訊同樣地，Lync 可用於 Outlook 行事曆的目前狀態資訊會自動更新。</span><span class="sxs-lookup"><span data-stu-id="1863d-106">For example, Lync presence information can be reported in Microsoft Outlook; likewise, Lync can use Outlook calendar to automatically update that presence information.</span></span> <span data-ttu-id="1863d-107">（例如，Lync 可以變更您的狀態為忙碌任何時間行事曆中顯示您已排定的會議。）雖然您不需要執行 Exchange，以執行 Lync Server （反之亦然） 沒有小有疑問，同時使用這兩項產品 epitomizes 非常術語的定義更妥善地 」 放在一起。 」</span><span class="sxs-lookup"><span data-stu-id="1863d-107">(For example, Lync can change your status to Busy any time your calendar shows that you have a meeting scheduled.) Although you do not have to run Exchange in order to run Lync Server (or vice-versa) there's little doubt that using the two products together epitomizes the very definition of the term "better together."</span></span>

<span data-ttu-id="1863d-108">特別是與 Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013 的版本。</span><span class="sxs-lookup"><span data-stu-id="1863d-108">This is especially true with the release of Microsoft Lync Server 2013 and Microsoft Exchange Server 2013.</span></span> <span data-ttu-id="1863d-109">除了功能，例如整合通訊和 IM 和目前狀態，Microsoft Exchange Server 2010 和 Microsoft Lync Server 2010 中找到的伺服器產品的 2013年版本會包含新功能的數的字。</span><span class="sxs-lookup"><span data-stu-id="1863d-109">In addition to features, such as unified messaging and IM and presence, that are found in Microsoft Exchange Server 2010 and Microsoft Lync Server 2010, the 2013 releases of the server products include a number of new capabilities.</span></span> <span data-ttu-id="1863d-110">這些功能包含下列項目：</span><span class="sxs-lookup"><span data-stu-id="1863d-110">These capabilities include such things as:</span></span>

  - <span data-ttu-id="1863d-111">**Lync 封存整合**。</span><span class="sxs-lookup"><span data-stu-id="1863d-111">**Lync Archiving Integration**.</span></span> <span data-ttu-id="1863d-112">Lync Server 2013 中的系統管理員仍然可以選擇讓立即訊息和 Web 會議記錄封存至 SQL Server （這些記錄已封存 Lync Server 2010 中的相同方式）。</span><span class="sxs-lookup"><span data-stu-id="1863d-112">In Lync Server 2013 administrators still have the option of having instant messaging and Web conferencing transcripts archived to SQL Server (the same way these transcripts were archived in Lync Server 2010).</span></span> <span data-ttu-id="1863d-113">或者，不過，系統管理員可以選擇讓記錄封存至 Exchange 2013 中，將這些記錄之個別使用者信箱中儲存在 Exchange 中封存的通訊的方式相同。</span><span class="sxs-lookup"><span data-stu-id="1863d-113">Alternatively, however, administrators can choose to have transcripts archived to Exchange 2013, storing those transcripts in the individual user mailboxes in the same way in which Exchange archives communications.</span></span> <span data-ttu-id="1863d-114">這表示在單一存放庫的所有電子通訊 （從 Exchange 和 Lync 伺服器），讓更容易搜尋並擷取這些封存的通訊應該需要發生。</span><span class="sxs-lookup"><span data-stu-id="1863d-114">That means a single repository for all your electronic communications (from both Exchange and Lync Server), which makes it much easier to search for and retrieve those archived communications should the need arise.</span></span>

  - <span data-ttu-id="1863d-115">**整合的連絡人存放區**。</span><span class="sxs-lookup"><span data-stu-id="1863d-115">**Unified Contact Store**.</span></span> <span data-ttu-id="1863d-116">在 Lync Server 2010 中，使用者必須維護在 Outlook 和 Lync; 中的個別連絡人清單事實上，以確保您具有相同您必須維護重複這兩個產品中可用的連絡人連絡清單，一個適用於 Outlook，一個 lync。</span><span class="sxs-lookup"><span data-stu-id="1863d-116">In Lync Server 2010, users had to maintain separate contact lists in Outlook and Lync; in fact, to ensure that you had the same contacts available in both products you had to maintain duplicate contact lists, one for Outlook and one for Lync.</span></span> <span data-ttu-id="1863d-117">搭配 Lync Server 2013，不過，使用者的連絡人可以儲存在 Exchange 2013 和整合連絡人存放區。</span><span class="sxs-lookup"><span data-stu-id="1863d-117">With Lync Server 2013, however, user contacts can be stored in Exchange 2013 and the unified contact store.</span></span> <span data-ttu-id="1863d-118">使用單一的連絡人存放區可讓使用者維護與連絡人不會出現在 Lync 2013、 Outlook 2013 和 Outlook Web Access 2013 中的同一組只是一組連絡人。</span><span class="sxs-lookup"><span data-stu-id="1863d-118">Using a single contact store enables users to maintain just one set of contacts, with that same set of contacts being available in Lync 2013, Outlook 2013, and Outlook Web Access 2013.</span></span>

  - <span data-ttu-id="1863d-119">**從 OWA 排程 Lync 會議**。</span><span class="sxs-lookup"><span data-stu-id="1863d-119">**Lync Meeting Scheduling from OWA**.</span></span> <span data-ttu-id="1863d-120">與 Lync Server 2013 和 Exchange 2013 整合，使用者可以排程 Lync 會議，從 Outlook Web Access 2013。</span><span class="sxs-lookup"><span data-stu-id="1863d-120">With Lync Server 2013 and Exchange 2013 integration, users can schedule Lync meetings from Outlook Web Access 2013.</span></span>

  - <span data-ttu-id="1863d-121">**高解析度相片**。</span><span class="sxs-lookup"><span data-stu-id="1863d-121">**High resolution photos**.</span></span> <span data-ttu-id="1863d-122">Lync 2010 可能只會顯示小型的連絡人; 相片這是因為這些相片被儲存在 Active Directory，以及 Active Directory 施加 48 個像素的預存的相片 48 個像素大小限制。</span><span class="sxs-lookup"><span data-stu-id="1863d-122">Lync 2010 could only display small photos of your contacts; that's because those photos were stored in Active Directory, and Active Directory imposes a 48 pixel by 48 pixel size limitation on stored photos.</span></span> <span data-ttu-id="1863d-123">搭配 Lync Server 2013，不過，相片可以儲存在 Microsoft Exchange;可讓高解析度相片高達 648 像素 x 648 像素為單位。</span><span class="sxs-lookup"><span data-stu-id="1863d-123">With Lync Server 2013, however, photos can be stored in Microsoft Exchange; that allows for high-resolution photos as large as 648 pixels by 648 pixels.</span></span> <span data-ttu-id="1863d-124">如您所預期，Lync 2013 已升級為允許這些高解析度相片的顯示。</span><span class="sxs-lookup"><span data-stu-id="1863d-124">As you might expect, Lync 2013 has been upgraded to allow for the display of these high-resolution photographs.</span></span>

<span data-ttu-id="1863d-125">請記住，這些新功能需要使用 Lync Server 2013 和 Exchange 2013。</span><span class="sxs-lookup"><span data-stu-id="1863d-125">Keep in mind that these new features require the use of both Lync Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="1863d-126">所，希望能夠充分利用這些新功能的使用者必須能夠在 Lync Server 2013 和 Exchange 2013 的帳戶，且必須使用最新版的用戶端軟體 (例如，Lync 2013)。</span><span class="sxs-lookup"><span data-stu-id="1863d-126">In addition to that, users who hope to take full advantage of these new capabilities must have accounts on Lync Server 2013 and Exchange 2013, and must be using the latest versions of the client software (e.g., Lync 2013).</span></span> <span data-ttu-id="1863d-127">例如，且無法供具有已位於 Lync Server 2010; 使用者整合連絡人存放區同樣地，高解析度相片無法顯示在 Lync 2010。</span><span class="sxs-lookup"><span data-stu-id="1863d-127">For example, the unified contact store is not available to users who have been homed on Lync Server 2010; likewise, high-resolution photos cannot be displayed in Lync 2010.</span></span>

<span data-ttu-id="1863d-128">這份文件提供整合 Lync Server 2013 和 Exchange 2013 的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="1863d-128">This documentation provides information on integrating Lync Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="1863d-129">包括上啟用新功能，例如封存整合和整合連絡人存放區的逐步說明資訊。</span><span class="sxs-lookup"><span data-stu-id="1863d-129">including step-by-step information on enabling new features such archiving Integration and the unified contact store.</span></span> <span data-ttu-id="1863d-130">這份文件不會不做什麼是討論的初始安裝與設定下列兩項產品。</span><span class="sxs-lookup"><span data-stu-id="1863d-130">What this documentation does not do is discuss the initial setup and configuration of these two products.</span></span> <span data-ttu-id="1863d-131">如需 Lync Server 2013 部署的詳細資訊，請參閱 Lync Server 2013 技術中心，在[https://go.microsoft.com/fwlink/p/?LinkId=246127](https://go.microsoft.com/fwlink/p/?linkid=246127)。</span><span class="sxs-lookup"><span data-stu-id="1863d-131">For details about deploying Lync Server 2013 see the Lync Server 2013 Tech Center at [https://go.microsoft.com/fwlink/p/?LinkId=246127](https://go.microsoft.com/fwlink/p/?linkid=246127).</span></span> <span data-ttu-id="1863d-132">如需 Exchange 2013 部署的詳細資訊，請參閱在 Exchange 2013 Tech Center [https://go.microsoft.com/fwlink/p/?LinkId=268528](https://go.microsoft.com/fwlink/p/?linkid=268528)。</span><span class="sxs-lookup"><span data-stu-id="1863d-132">For details about deploying Exchange 2013 see the Exchange 2013 Tech Center at [https://go.microsoft.com/fwlink/p/?LinkId=268528](https://go.microsoft.com/fwlink/p/?linkid=268528).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="1863d-133">本章節內容</span><span class="sxs-lookup"><span data-stu-id="1863d-133">In This Section</span></span>

[<span data-ttu-id="1863d-134">整合 Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013 的必要條件</span><span class="sxs-lookup"><span data-stu-id="1863d-134">Prerequisites for integrating Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>](lync-server-2013-prerequisites-for-integrating-with-exchange-server-2013.md)

[<span data-ttu-id="1863d-135">Microsoft Lync Server 2013 和 Microsoft Exchange Server 2013 中設定夥伴應用程式</span><span class="sxs-lookup"><span data-stu-id="1863d-135">Configuring partner applications in Microsoft Lync Server 2013 and Microsoft Exchange Server 2013</span></span>](lync-server-2013-configuring-partner-applications-in-lync-server-2013-and-exchange-server-2013.md)

[<span data-ttu-id="1863d-136">設定 Microsoft Lync Server 2013 使用 Microsoft Exchange Server 2013 封存</span><span class="sxs-lookup"><span data-stu-id="1863d-136">Configuring Microsoft Lync Server 2013 to use Microsoft Exchange Server 2013 archiving</span></span>](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md)

[<span data-ttu-id="1863d-137">設定 Microsoft SharePoint Server 2013 搜尋已封存的 Microsoft Lync Server 2013 資料</span><span class="sxs-lookup"><span data-stu-id="1863d-137">Configuring Microsoft SharePoint Server 2013 to search for archived Microsoft Lync Server 2013 data</span></span>](lync-server-2013-configuring-microsoft-sharepoint-server-2013-to-search-for-archived-lync-server-2013-data.md)

[<span data-ttu-id="1863d-138">設定 Microsoft Lync Server 2013 使用整合連絡人存放區</span><span class="sxs-lookup"><span data-stu-id="1863d-138">Configuring Microsoft Lync Server 2013 to use the unified contact store</span></span>](lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md)

<span data-ttu-id="1863d-139">[在 [Microsoft Lync Server 2013 中設定使用高解析度相片](lync-server-2013-configuring-the-use-of-high-resolution-photos.md)</span><span class="sxs-lookup"><span data-stu-id="1863d-139">[Configuring the use of high-resolution photos in Microsoft Lync Server 2013](lync-server-2013-configuring-the-use-of-high-resolution-photos.md)</span></span>

[<span data-ttu-id="1863d-140">設定 Microsoft Exchange Server 2013 整合通訊的 Microsoft Lync Server 2013 語音信箱</span><span class="sxs-lookup"><span data-stu-id="1863d-140">Configuring Microsoft Exchange Server 2013 Unified Messaging for Microsoft Lync Server 2013 voice mail</span></span>](lync-server-2013-configuring-microsoft-exchange-server-2013-unified-messaging-for-lync-server-2013-voice-mail.md)

[<span data-ttu-id="1863d-141">整合 Microsoft Lync Server 2013 和 Microsoft Outlook Web App 2013</span><span class="sxs-lookup"><span data-stu-id="1863d-141">Integrating Microsoft Lync Server 2013 and Microsoft Outlook Web App 2013</span></span>](lync-server-2013-integrating-lync-server-and-outlook-web-app-2013.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

