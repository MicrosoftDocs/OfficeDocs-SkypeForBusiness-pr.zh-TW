---
title: Lync Server 2013：主控 Exchange 連絡人物件管理
description: Lync Server 2013：主控 Exchange 連絡人物件管理。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange Contact object management
ms:assetid: eead9d76-bc4f-4c1c-9779-683cb7a88410
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412978(v=OCS.15)
ms:contentKeyID: 48185748
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 691bcea10d3a4f8b523c6565f384d6c4c9a2a2a3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552769"
---
# <a name="hosted-exchange-contact-object-management-in-lync-server-2013"></a><span data-ttu-id="70075-103">Lync Server 2013 中的主控 Exchange 連絡人物件管理</span><span class="sxs-lookup"><span data-stu-id="70075-103">Hosted Exchange Contact object management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="70075-104">_**主題上次修改日期：** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="70075-104">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="70075-105">您必須針對跨單位部署中的每個自動語音應答號碼和使用者存取號碼，設定連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="70075-105">You need to configure a Contact object for each auto-attendant number and subscriber access number in your cross-premises deployment.</span></span>

<span data-ttu-id="70075-106">若要與主控 Exchange UM 整合，ocsumutil.exe 無法用來管理連絡人物件，因為這取決於 Active Directory Exchange UM 設定。</span><span class="sxs-lookup"><span data-stu-id="70075-106">For integration with hosted Exchange UM, ocsumutil.exe cannot be used to manage Contact objects, because it depends on Active Directory Exchange UM settings.</span></span> <span data-ttu-id="70075-107">在跨單位部署中，Lync Server 2013 和主控 Exchange UM 是安裝在不同的樹系中，彼此之間不具任何信任。</span><span class="sxs-lookup"><span data-stu-id="70075-107">In a cross-premises deployment, Lync Server 2013 and hosted Exchange UM are installed in separate forests with no trust between them.</span></span> <span data-ttu-id="70075-108">基於安全性原因，Lync Server 2013 系統管理員無法直接存取 Exchange UM Active Directory 設定。</span><span class="sxs-lookup"><span data-stu-id="70075-108">For security reasons, Lync Server 2013 administrators have no direct access to Exchange UM Active Directory settings.</span></span> <span data-ttu-id="70075-109">因此，Lync Server 2013 提供不同的模型，用以管理 Lync Server 2013 和主控 Exchange UM 服務可存取的 *共用 SIP 位址空間* 中的連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="70075-109">As a result, Lync Server 2013 provides a different model for managing Contact objects in a *shared SIP address space* that is accessible to both Lync Server 2013 and the hosted Exchange UM service.</span></span>

<div>

## <a name="hosted-contact-object-workflow"></a><span data-ttu-id="70075-110">主控的連絡人物件工作流程</span><span class="sxs-lookup"><span data-stu-id="70075-110">Hosted Contact Object Workflow</span></span>

<span data-ttu-id="70075-111">以下是與託管的 Exchange 租使用者管理員搭配使用以管理連絡人物件的一般步驟：</span><span class="sxs-lookup"><span data-stu-id="70075-111">The following are the general steps for working with your hosted Exchange tenant administrator to manage contact objects:</span></span>

1.  <span data-ttu-id="70075-112">Exchange 管理員要求 Exchange UM 訂戶存取和自動語音應答連絡人物件的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="70075-112">The Exchange administrator requests phone numbers for the Exchange UM subscriber access and auto-attendant Contact objects.</span></span>

2.  <span data-ttu-id="70075-113">Lync Server 2013 系統管理員會為每個電話號碼建立連絡人物件，並將主控的語音信箱原則指派給每個連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="70075-113">The Lync Server 2013 administrator creates a Contact object for each phone number and assigns a hosted voice mail policy to each Contact object.</span></span>

3.  <span data-ttu-id="70075-114">Lync Server 2013 系統管理員會為 Exchange 系統管理員提供電話號碼。</span><span class="sxs-lookup"><span data-stu-id="70075-114">The Lync Server 2013 administrator provides the phone numbers to the Exchange administrator.</span></span>

4.  <span data-ttu-id="70075-115">Exchange 管理員會將電話號碼指派給適當的 Exchange UM 撥號對應表，以供自動語音應答和訂戶存取。</span><span class="sxs-lookup"><span data-stu-id="70075-115">The Exchange administrator assigns the phone numbers to appropriate Exchange UM dial plans for auto attendants and subscriber access.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="70075-116">您不需要在連絡人物件上設定任何 Lync Server 2013 撥號對應表設定，就像內部部署部署一樣。</span><span class="sxs-lookup"><span data-stu-id="70075-116">There is no need to configure any Lync Server 2013 dial plan settings on the Contact objects as there is with on-premises deployments.</span></span>



</div>

</div>

<div>

## <a name="configuring-hosted-contact-objects"></a><span data-ttu-id="70075-117">設定主控的連絡人物件</span><span class="sxs-lookup"><span data-stu-id="70075-117">Configuring Hosted Contact Objects</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="70075-118">在 Lync Server 2013 的連絡人物件可供主控 Exchange UM 啟用之前，必須先部署適用于這些物件的主控語音信箱原則。</span><span class="sxs-lookup"><span data-stu-id="70075-118">Before Lync Server 2013 Contact objects can be enabled for hosted Exchange UM, a hosted voice mail policy that applies to them must be deployed.</span></span> <span data-ttu-id="70075-119">原則可以是全域、網站層級或個別使用者範圍，只要套用至您想要啟用的連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="70075-119">The policy can be of global, site-level, or per-user scope, as long as it applies to the contact object you want to enable.</span></span> <span data-ttu-id="70075-120">如需詳細資訊，請參閱 <A href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013 中的主控語音信箱原則</A>。</span><span class="sxs-lookup"><span data-stu-id="70075-120">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="70075-121">若要在跨部署部署中設定主控的自動語音應答和訂戶存取連絡人物件，您必須使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="70075-121">To configure hosted auto-attendant and subscriber access Contact objects in a cross-premises deployment, you must use the following cmdlets:</span></span>

  - <span data-ttu-id="70075-122">**New-CsExUmContact** 會為主控的 UM 建立新的連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="70075-122">**New-CsExUmContact** creates a new Contact object for hosted UM.</span></span>

  - <span data-ttu-id="70075-123">**Set-CsExUmContact** 會修改主控 Exchange UM 的現有連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="70075-123">**Set-CsExUmContact** modifies an existing Contact object for hosted Exchange UM.</span></span>

<span data-ttu-id="70075-124">下列範例會建立自動語音應答連絡人物件：</span><span class="sxs-lookup"><span data-stu-id="70075-124">The following example creates an auto-attendant Contact object:</span></span>

    New-CsExUmContact -SipAddress sip:exumaa1@fabrikam.com -RegistrarPool RedmondPool.litwareinc.com -OU "OU=ExUmContacts,DC=litwareinc,DC=com" -DisplayNumber 2065559876 -AutoAttendant $True

<span data-ttu-id="70075-125">此範例會使用 SIP 位址 sip:exumaa1@fabrikam.com 來建立新的 Exchange UM 連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="70075-125">This example creates a new Exchange UM Contact object with the SIP address sip:exumaa1@fabrikam.com.</span></span> <span data-ttu-id="70075-126">Lync Server 2013 註冊服務所在的集區名稱是 RedmondPool.litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="70075-126">The name of the pool where the Lync Server 2013 Registrar service is running is RedmondPool.litwareinc.com.</span></span> <span data-ttu-id="70075-127">儲存此資訊的 Active Directory 組織單位為 OU = ExUmContacts，DC = litwareinc，DC=com。</span><span class="sxs-lookup"><span data-stu-id="70075-127">The Active Directory organizational unit where this information will be stored is OU=ExUmContacts,DC=litwareinc,DC=com.</span></span> <span data-ttu-id="70075-128">連絡人物件的電話號碼是2065554567。</span><span class="sxs-lookup"><span data-stu-id="70075-128">The phone number of the Contact object is 2065554567.</span></span> <span data-ttu-id="70075-129">Optional-AutoAttendant $True 參數會指定此物件為自動語音應答連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="70075-129">The optional -AutoAttendant $True parameter specifies that this object is an auto-attendant Contact object.</span></span> <span data-ttu-id="70075-130">將-AutoAttendant 參數設定為 False (default) 會指定訂戶存取連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="70075-130">Setting the -AutoAttendant parameter to False (the default) specifies a subscriber access Contact object.</span></span>

<span data-ttu-id="70075-131">如需 New-CsExUmContact 和 Set-CsExUmContact Cmdlet 的詳細資訊，請參閱 Lync Server 管理命令介面檔。</span><span class="sxs-lookup"><span data-stu-id="70075-131">For details about the New-CsExUmContact and Set-CsExUmContact cmdlets, see the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

