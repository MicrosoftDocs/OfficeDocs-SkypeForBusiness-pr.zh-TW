---
title: 'Lync Server 2013: Exchange 與 SharePoint 整合支援'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Exchange and SharePoint integration support
ms:assetid: 72bf8aa5-55b1-4851-8a59-c96bf85d215a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205005(v=OCS.15)
ms:contentKeyID: 48184504
ms.date: 01/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 566af847bb177173f91634b9b46cceae1d9c88ea
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035115"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="exchange-and-sharepoint-integration-support-in-lync-server-2013"></a><span data-ttu-id="2b0a3-102">Lync Server 2013 中的 Exchange 和 SharePoint 整合支援</span><span class="sxs-lookup"><span data-stu-id="2b0a3-102">Exchange and SharePoint integration support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b0a3-103">_**主題上次修改日期：** 2017年-01-18_</span><span class="sxs-lookup"><span data-stu-id="2b0a3-103">_**Topic Last Modified:** 2017-01-18_</span></span>

<span data-ttu-id="2b0a3-104">Lync Server 2013 和 Lync 2013 可以安全地傳達順暢地與其他應用程式和伺服器產品，包括 Office 2013、 Exchange Server 2013、 Exchange Server 2016 和 SharePoint 中，如果您在整合這些產品。</span><span class="sxs-lookup"><span data-stu-id="2b0a3-104">Lync Server 2013 and Lync 2013 can securely and seamlessly communicate with other applications and server products, including Office 2013, Exchange Server 2013, Exchange Server 2016, and SharePoint, if you integrate these products.</span></span> <span data-ttu-id="2b0a3-105">整合 Lync Server 2013 和 Office 提供的內容存取的使用者的立即訊息 (IM)、 增強顯示狀態、 電話語音] 和 Lync 會議功能。</span><span class="sxs-lookup"><span data-stu-id="2b0a3-105">Integrating Lync Server 2013 and Office provides users with in-context access to the instant messaging (IM), enhanced presence, telephony, and conferencing capabilities of Lync.</span></span> <span data-ttu-id="2b0a3-106">Office 使用者可以存取 Lync 功能從 Outlook 2013 通訊和共同作業用戶端和其他 Office 程式中，或是從 SharePoint] 頁面。</span><span class="sxs-lookup"><span data-stu-id="2b0a3-106">Office users can access Lync features from within the Outlook 2013 messaging and collaboration client and other Office programs or from a SharePoint page.</span></span> <span data-ttu-id="2b0a3-107">使用者也可以檢視 Lync 交談記錄中的 Outlook 交談歷程記錄資料夾。</span><span class="sxs-lookup"><span data-stu-id="2b0a3-107">Users can also view a record of Lync conversations in the Outlook Conversation History folder.</span></span> <span data-ttu-id="2b0a3-108">當與 Exchange 2013、 Exchange 2016 或 Exchange Online 整合，Lync Server 2013 也支援下列項目：</span><span class="sxs-lookup"><span data-stu-id="2b0a3-108">When integrated with Exchange 2013, Exchange 2016, or Exchange Online, Lync Server 2013 also supports the following:</span></span>

  - <span data-ttu-id="2b0a3-109">整合連絡人存放區，讓使用者可以將所有聯絡人資訊儲存在 Exchange 或 Exchange Online，以便資訊皆可全域 Lync 2013、 Exchange、 Outlook 和 Outlook Web App。</span><span class="sxs-lookup"><span data-stu-id="2b0a3-109">Unified contact store, which enables users to store all contact information in Exchange or Exchange Online so that the information is available globally across Lync 2013, Exchange, Outlook, and Outlook Web App.</span></span>

  - <span data-ttu-id="2b0a3-110">交談歷程記錄和 Web 會議歷程記錄，也就是在 Exchange 中儲存使用者資料夾。</span><span class="sxs-lookup"><span data-stu-id="2b0a3-110">Conversation history and Web conferencing history, which is stored in Exchange user folders.</span></span>

  - <span data-ttu-id="2b0a3-111">從 Lync IM 和會議內容，例如封存的內容可以儲存在 Exchange 儲存區。</span><span class="sxs-lookup"><span data-stu-id="2b0a3-111">Archived content from Lync, such as IM and meeting content, can be stored in Exchange storage.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2b0a3-112">Lync Server 2013 支援與舊版 Microsoft Exchange Server 與 SharePoint Server 的整合，但這些先前的版本，例如封存存放區與 Microsoft Exchange 整合支援並非所有的功能。</span><span class="sxs-lookup"><span data-stu-id="2b0a3-112">Lync Server 2013 supports integration with previous versions of Microsoft Exchange Server and SharePoint Server, but not all functionality is supported with these previous versions, such as integration of Archiving storage with Microsoft Exchange.</span></span><BR><span data-ttu-id="2b0a3-113">如果您將您的使用者移轉至 Exchange 2013 或 Exchange 2016，您可以使用 Exchange 儲存區與 Lync Server 儲存區基礎過渡，當您完成移轉。</span><span class="sxs-lookup"><span data-stu-id="2b0a3-113">If you are migrating your users to Exchange 2013 or Exchange 2016, you can use both Exchange storage and Lync Server storage on an interim basis, while you complete the migration.</span></span> <span data-ttu-id="2b0a3-114">不支援永久使用 Exchange 與 Lync Server 儲存區。</span><span class="sxs-lookup"><span data-stu-id="2b0a3-114">Permanent use of both Exchange and Lync Server storage is not supported.</span></span>



</div>

<span data-ttu-id="2b0a3-115">整合的 Lync Server 2013 與 Exchange Server 和 SharePoint Server 需要執行 Lync Server 2013、 Exchange Server 和 SharePoint Server 的伺服器之間的伺服器對伺服器驗證。</span><span class="sxs-lookup"><span data-stu-id="2b0a3-115">Integration of Lync Server 2013 with Exchange Server and SharePoint Server requires server-to-server authentication between servers running Lync Server 2013, Exchange Server, and SharePoint Server.</span></span> <span data-ttu-id="2b0a3-116">Lync Server 2013 支援伺服器對伺服器驗證及授權的 OAuth (Open Authorization) 通訊協定。</span><span class="sxs-lookup"><span data-stu-id="2b0a3-116">Lync Server 2013 supports OAuth (Open Authorization) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="2b0a3-117">針對 Microsoft 伺服器之間的內部部署伺服器對伺服器驗證，並不需要使用協力廠商 Token 伺服器。</span><span class="sxs-lookup"><span data-stu-id="2b0a3-117">For on-premises server-to-server authentication between two Microsoft servers, there is no need to use a third-party token server.</span></span> <span data-ttu-id="2b0a3-118">Lync Server 2013、 Exchange Server 和 SharePoint Server 具有內建的權杖伺服器可以用於驗證目的彼此。</span><span class="sxs-lookup"><span data-stu-id="2b0a3-118">Lync Server 2013, Exchange Server, and SharePoint Server have a built-in token server that can be used for authentication purposes with each other.</span></span> <span data-ttu-id="2b0a3-119">例如，Lync Server 2013 可以發出簽署安全性權杖由本身，並與 Exchange 進行通訊時使用該權杖。</span><span class="sxs-lookup"><span data-stu-id="2b0a3-119">For example, Lync Server 2013 can issue and sign a security token by itself, and use that token when communicating with Exchange.</span></span> <span data-ttu-id="2b0a3-120">在此情況下，則不需要使用協力廠商 Token 伺服器。</span><span class="sxs-lookup"><span data-stu-id="2b0a3-120">In this case, there is no need to use a third-party token server.</span></span>

<span data-ttu-id="2b0a3-121">Lync Server 2013 支援兩個伺服器對伺服器驗證案例。</span><span class="sxs-lookup"><span data-stu-id="2b0a3-121">Lync Server 2013 supports the two server-to-server authentication scenarios.</span></span> <span data-ttu-id="2b0a3-122">這些功能包括下列之間的伺服器對伺服器驗證的設定：</span><span class="sxs-lookup"><span data-stu-id="2b0a3-122">These include configuration of server-to-server authentication between the following:</span></span>

  - <span data-ttu-id="2b0a3-123">Lync Server 2013 和 Exchange Server 2013、 Exchange Server 2016、 和/或 SharePoint Server 的內部部署安裝的內部部署安裝。</span><span class="sxs-lookup"><span data-stu-id="2b0a3-123">An on-premise installation of Lync Server 2013 and an on-premises installation of Exchange Server 2013, Exchange Server 2016, and/or SharePoint Server.</span></span>

  - <span data-ttu-id="2b0a3-124">一組 Office 元件 （例如，Microsoft Exchange 365 和 Microsoft Lync Server 365，之間或 Microsoft Lync Server 365 及 Microsoft SharePoint 365 之間）。</span><span class="sxs-lookup"><span data-stu-id="2b0a3-124">A pair of Office components (for example, between Microsoft Exchange 365 and Microsoft Lync Server 365, or between Microsoft Lync Server 365 and Microsoft SharePoint 365).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2b0a3-125">此 Lync Server 2013 版本不支援在內部伺服器與 Office 365 元件之間的伺服器對伺服器驗證。</span><span class="sxs-lookup"><span data-stu-id="2b0a3-125">Server-to-server authentication between an on-premises server and an Office 365 component is not supported in this Lync Server 2013 release.</span></span> <span data-ttu-id="2b0a3-126">除此之外，這表示您無法設定內部部署安裝 Lync Server 2013 和 Microsoft Exchange 365 之間的伺服器對伺服器驗證。</span><span class="sxs-lookup"><span data-stu-id="2b0a3-126">Among other things, this means that you cannot set up server-to-server authentication between an on-premises installation of Lync Server 2013 and Microsoft Exchange 365.</span></span>



</div>

<span data-ttu-id="2b0a3-127">如需有關伺服器對伺服器驗證的詳細資訊，請參閱部署文件或作業文件中的[管理伺服器對伺服器驗證 (OAuth) 與 Lync Server 2013 中的協力廠商應用程式](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="2b0a3-127">For details about server-to-server authentication, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in the Deployment documentation or Operations documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

