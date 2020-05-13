---
title: Lync Server 2013： Exchange 和 SharePoint 整合支援
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
ms.openlocfilehash: 262e31ac6049920ca4e327f50dccaae18d69a2f5
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221717"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="exchange-and-sharepoint-integration-support-in-lync-server-2013"></a><span data-ttu-id="9553f-102">Lync Server 2013 中的 Exchange 和 SharePoint 整合支援</span><span class="sxs-lookup"><span data-stu-id="9553f-102">Exchange and SharePoint integration support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9553f-103">_**主題上次修改日期：** 2017-01-18_</span><span class="sxs-lookup"><span data-stu-id="9553f-103">_**Topic Last Modified:** 2017-01-18_</span></span>

<span data-ttu-id="9553f-104">當您整合這些產品時，lync Server 2013 和 Lync 2013 可以與其他應用程式和伺服器產品（包括 Office 2013、Exchange Server 2013、Exchange Server 2016 及 SharePoint）安全且順利地通訊。</span><span class="sxs-lookup"><span data-stu-id="9553f-104">Lync Server 2013 and Lync 2013 can securely and seamlessly communicate with other applications and server products, including Office 2013, Exchange Server 2013, Exchange Server 2016, and SharePoint, if you integrate these products.</span></span> <span data-ttu-id="9553f-105">整合 Lync Server 2013 和 Office 提供使用者對立即訊息（IM）、增強型顯示狀態、電話語音功能的存取，以及 Lync 的會議功能。</span><span class="sxs-lookup"><span data-stu-id="9553f-105">Integrating Lync Server 2013 and Office provides users with in-context access to the instant messaging (IM), enhanced presence, telephony, and conferencing capabilities of Lync.</span></span> <span data-ttu-id="9553f-106">Office 使用者可以從 Outlook 2013 訊息與共同作業用戶端和其他 Office 程式或從 SharePoint 頁面存取 Lync 功能。</span><span class="sxs-lookup"><span data-stu-id="9553f-106">Office users can access Lync features from within the Outlook 2013 messaging and collaboration client and other Office programs or from a SharePoint page.</span></span> <span data-ttu-id="9553f-107">使用者也可以在 [Outlook 交談記錄] 資料夾中查看 Lync 交談記錄。</span><span class="sxs-lookup"><span data-stu-id="9553f-107">Users can also view a record of Lync conversations in the Outlook Conversation History folder.</span></span> <span data-ttu-id="9553f-108">當與 Exchange 2013、Exchange 2016 或 Exchange Online 整合時，Lync Server 2013 也支援下列各項：</span><span class="sxs-lookup"><span data-stu-id="9553f-108">When integrated with Exchange 2013, Exchange 2016, or Exchange Online, Lync Server 2013 also supports the following:</span></span>

  - <span data-ttu-id="9553f-109">整合連絡人存放區，可讓使用者在 Exchange 或 Exchange Online 中儲存所有連絡人資訊，使其可在 Lync 2013、Exchange、Outlook 和 Outlook Web App 之間取得全域資訊。</span><span class="sxs-lookup"><span data-stu-id="9553f-109">Unified contact store, which enables users to store all contact information in Exchange or Exchange Online so that the information is available globally across Lync 2013, Exchange, Outlook, and Outlook Web App.</span></span>

  - <span data-ttu-id="9553f-110">[交談記錄] 和 [Web 會議史] （儲存在 Exchange 使用者資料夾中）。</span><span class="sxs-lookup"><span data-stu-id="9553f-110">Conversation history and Web conferencing history, which is stored in Exchange user folders.</span></span>

  - <span data-ttu-id="9553f-111">Lync 的封存內容（例如 IM 和會議內容）可以儲存在 Exchange 儲存區中。</span><span class="sxs-lookup"><span data-stu-id="9553f-111">Archived content from Lync, such as IM and meeting content, can be stored in Exchange storage.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9553f-112">Lync Server 2013 可支援與舊版的 Microsoft Exchange Server 和 SharePoint Server 整合，但並非這些舊版的支援，例如與 Microsoft Exchange 整合存放的功能。</span><span class="sxs-lookup"><span data-stu-id="9553f-112">Lync Server 2013 supports integration with previous versions of Microsoft Exchange Server and SharePoint Server, but not all functionality is supported with these previous versions, such as integration of Archiving storage with Microsoft Exchange.</span></span><BR><span data-ttu-id="9553f-113">若要將使用者遷移至 Exchange 2013 或 Exchange 2016，您可以在完成遷移時，定期使用 Exchange storage 和 Lync Server storage。</span><span class="sxs-lookup"><span data-stu-id="9553f-113">If you are migrating your users to Exchange 2013 or Exchange 2016, you can use both Exchange storage and Lync Server storage on an interim basis, while you complete the migration.</span></span> <span data-ttu-id="9553f-114">不支援永久使用 Exchange 和 Lync Server 存放區。</span><span class="sxs-lookup"><span data-stu-id="9553f-114">Permanent use of both Exchange and Lync Server storage is not supported.</span></span>



</div>

<span data-ttu-id="9553f-115">將 Lync Server 2013 與 Exchange Server 和 SharePoint Server 整合，需要執行 Lync Server 2013、Exchange Server 和 SharePoint Server 的伺服器之間的伺服器對伺服器驗證。</span><span class="sxs-lookup"><span data-stu-id="9553f-115">Integration of Lync Server 2013 with Exchange Server and SharePoint Server requires server-to-server authentication between servers running Lync Server 2013, Exchange Server, and SharePoint Server.</span></span> <span data-ttu-id="9553f-116">Lync Server 2013 支援伺服器對伺服器驗證和授權的 OAuth （開放授權）通訊協定。</span><span class="sxs-lookup"><span data-stu-id="9553f-116">Lync Server 2013 supports OAuth (Open Authorization) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="9553f-117">針對 Microsoft 伺服器之間的內部部署伺服器對伺服器驗證，並不需要使用協力廠商 Token 伺服器。</span><span class="sxs-lookup"><span data-stu-id="9553f-117">For on-premises server-to-server authentication between two Microsoft servers, there is no need to use a third-party token server.</span></span> <span data-ttu-id="9553f-118">Lync Server 2013、Exchange Server 和 SharePoint 伺服器都有內建的權杖伺服器，可用於彼此進行驗證。</span><span class="sxs-lookup"><span data-stu-id="9553f-118">Lync Server 2013, Exchange Server, and SharePoint Server have a built-in token server that can be used for authentication purposes with each other.</span></span> <span data-ttu-id="9553f-119">例如，Lync Server 2013 可以自行發行和簽署安全性權杖，並在與 Exchange 通訊時使用該權杖。</span><span class="sxs-lookup"><span data-stu-id="9553f-119">For example, Lync Server 2013 can issue and sign a security token by itself, and use that token when communicating with Exchange.</span></span> <span data-ttu-id="9553f-120">在此情況下，則不需要使用協力廠商 Token 伺服器。</span><span class="sxs-lookup"><span data-stu-id="9553f-120">In this case, there is no need to use a third-party token server.</span></span>

<span data-ttu-id="9553f-121">Lync Server 2013 支援兩種伺服器對伺服器驗證案例。</span><span class="sxs-lookup"><span data-stu-id="9553f-121">Lync Server 2013 supports the two server-to-server authentication scenarios.</span></span> <span data-ttu-id="9553f-122">這包括設定下列各項之間的伺服器對伺服器驗證：</span><span class="sxs-lookup"><span data-stu-id="9553f-122">These include configuration of server-to-server authentication between the following:</span></span>

  - <span data-ttu-id="9553f-123">Lync Server 2013 的內部部署安裝和 Exchange Server 2013、Exchange Server 2016 和/或 SharePoint 伺服器的內部部署安裝。</span><span class="sxs-lookup"><span data-stu-id="9553f-123">An on-premise installation of Lync Server 2013 and an on-premises installation of Exchange Server 2013, Exchange Server 2016, and/or SharePoint Server.</span></span>

  - <span data-ttu-id="9553f-124">一對 Office 元件（例如，在 Microsoft Exchange 365 和 Microsoft Lync Server 365 之間，或 Microsoft Lync Server 365 和 Microsoft SharePoint 365）。</span><span class="sxs-lookup"><span data-stu-id="9553f-124">A pair of Office components (for example, between Microsoft Exchange 365 and Microsoft Lync Server 365, or between Microsoft Lync Server 365 and Microsoft SharePoint 365).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9553f-125">在此 Lync Server 2013 版本中不支援內部部署伺服器與 Microsoft 365 或 Office 365 元件之間的伺服器對伺服器驗證。</span><span class="sxs-lookup"><span data-stu-id="9553f-125">Server-to-server authentication between an on-premises server and a Microsoft 365 or Office 365 component is not supported in this Lync Server 2013 release.</span></span> <span data-ttu-id="9553f-126">此外，這表示您無法設定 Lync Server 2013 和 Microsoft Exchange 365 的內部部署安裝之間的伺服器對伺服器驗證。</span><span class="sxs-lookup"><span data-stu-id="9553f-126">Among other things, this means that you cannot set up server-to-server authentication between an on-premises installation of Lync Server 2013 and Microsoft Exchange 365.</span></span>



</div>

<span data-ttu-id="9553f-127">如需伺服器對伺服器驗證的詳細資訊，請參閱部署檔或作業檔中的[管理 Lync server 2013 中的伺服器對伺服器驗證（OAuth）和夥伴應用程式](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="9553f-127">For details about server-to-server authentication, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in the Deployment documentation or Operations documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>
