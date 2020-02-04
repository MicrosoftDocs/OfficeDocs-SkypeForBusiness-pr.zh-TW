---
title: Lync Server 2013：主控 Exchange 聯絡人物件管理
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
ms.openlocfilehash: c63e9952abab192e7f8f4a71e97a660d2798d3b9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739063"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-contact-object-management-in-lync-server-2013"></a><span data-ttu-id="418b3-102">Lync Server 2013 中的主控 Exchange 聯絡人物件管理</span><span class="sxs-lookup"><span data-stu-id="418b3-102">Hosted Exchange Contact object management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="418b3-103">_**主題上次修改日期：** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="418b3-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="418b3-104">您必須針對跨平臺部署中的每個自動助理編號和訂閱者存取號碼設定連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="418b3-104">You need to configure a Contact object for each auto-attendant number and subscriber access number in your cross-premises deployment.</span></span>

<span data-ttu-id="418b3-105">若要與託管 Exchange UM 整合，ocsumutil 無法用來管理連絡人物件，因為它依賴 Active Directory Exchange UM 設定。</span><span class="sxs-lookup"><span data-stu-id="418b3-105">For integration with hosted Exchange UM, ocsumutil.exe cannot be used to manage Contact objects, because it depends on Active Directory Exchange UM settings.</span></span> <span data-ttu-id="418b3-106">在跨內部部署中，Lync Server 2013 和託管 Exchange UM 會安裝在不同的林中，且不受信任。</span><span class="sxs-lookup"><span data-stu-id="418b3-106">In a cross-premises deployment, Lync Server 2013 and hosted Exchange UM are installed in separate forests with no trust between them.</span></span> <span data-ttu-id="418b3-107">出於安全考慮，Lync Server 2013 系統管理員無法直接存取 Exchange UM Active Directory 設定。</span><span class="sxs-lookup"><span data-stu-id="418b3-107">For security reasons, Lync Server 2013 administrators have no direct access to Exchange UM Active Directory settings.</span></span> <span data-ttu-id="418b3-108">因此，Lync Server 2013 提供不同的模型，可在 Lync Server 2013 和託管 Exchange UM 服務的*共用 SIP 位址空間*中管理連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="418b3-108">As a result, Lync Server 2013 provides a different model for managing Contact objects in a *shared SIP address space* that is accessible to both Lync Server 2013 and the hosted Exchange UM service.</span></span>

<div>

## <a name="hosted-contact-object-workflow"></a><span data-ttu-id="418b3-109">託管連絡人物件工作流程</span><span class="sxs-lookup"><span data-stu-id="418b3-109">Hosted Contact Object Workflow</span></span>

<span data-ttu-id="418b3-110">以下是使用託管 Exchange 租使用者系統管理員來管理連絡人物件的一般步驟：</span><span class="sxs-lookup"><span data-stu-id="418b3-110">The following are the general steps for working with your hosted Exchange tenant administrator to manage contact objects:</span></span>

1.  <span data-ttu-id="418b3-111">Exchange 管理員會要求 Exchange UM 訂閱者存取及自動助理連絡人物件的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="418b3-111">The Exchange administrator requests phone numbers for the Exchange UM subscriber access and auto-attendant Contact objects.</span></span>

2.  <span data-ttu-id="418b3-112">Lync Server 2013 系統管理員會針對每個電話號碼建立連絡人物件，並將託管的語音信箱原則指派給每一個連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="418b3-112">The Lync Server 2013 administrator creates a Contact object for each phone number and assigns a hosted voice mail policy to each Contact object.</span></span>

3.  <span data-ttu-id="418b3-113">Lync Server 2013 系統管理員會將電話號碼提供給 Exchange 系統管理員。</span><span class="sxs-lookup"><span data-stu-id="418b3-113">The Lync Server 2013 administrator provides the phone numbers to the Exchange administrator.</span></span>

4.  <span data-ttu-id="418b3-114">Exchange 管理員會將電話號碼指派給適當的 Exchange UM 撥號方案，以進行自動語音應答及訂閱者存取。</span><span class="sxs-lookup"><span data-stu-id="418b3-114">The Exchange administrator assigns the phone numbers to appropriate Exchange UM dial plans for auto attendants and subscriber access.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="418b3-115">您不需要在連絡人物件上設定任何 Lync Server 2013 撥號方案設定，就像內部部署部署一樣。</span><span class="sxs-lookup"><span data-stu-id="418b3-115">There is no need to configure any Lync Server 2013 dial plan settings on the Contact objects as there is with on-premises deployments.</span></span>



</div>

</div>

<div>

## <a name="configuring-hosted-contact-objects"></a><span data-ttu-id="418b3-116">設定託管連絡人物件</span><span class="sxs-lookup"><span data-stu-id="418b3-116">Configuring Hosted Contact Objects</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="418b3-117">在 Lync Server 2013 連絡人物件可供託管 Exchange UM 使用之前，必須先部署適用于它們的託管語音信箱原則。</span><span class="sxs-lookup"><span data-stu-id="418b3-117">Before Lync Server 2013 Contact objects can be enabled for hosted Exchange UM, a hosted voice mail policy that applies to them must be deployed.</span></span> <span data-ttu-id="418b3-118">原則可以是全域、網站層級或每使用者範圍，只要它套用至您要啟用的連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="418b3-118">The policy can be of global, site-level, or per-user scope, as long as it applies to the contact object you want to enable.</span></span> <span data-ttu-id="418b3-119">如需詳細資訊，請參閱<A href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013 中託管的語音信箱原則</A>。</span><span class="sxs-lookup"><span data-stu-id="418b3-119">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="418b3-120">若要在跨內部部署中設定託管的自動助理及訂閱者存取連絡人物件，您必須使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="418b3-120">To configure hosted auto-attendant and subscriber access Contact objects in a cross-premises deployment, you must use the following cmdlets:</span></span>

  - <span data-ttu-id="418b3-121">[**新-CsExUmContact** ] 會為 [託管 UM] 建立新的連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="418b3-121">**New-CsExUmContact** creates a new Contact object for hosted UM.</span></span>

  - <span data-ttu-id="418b3-122">[**設定] CsExUmContact**會修改託管 Exchange UM 的現有連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="418b3-122">**Set-CsExUmContact** modifies an existing Contact object for hosted Exchange UM.</span></span>

<span data-ttu-id="418b3-123">下列範例會建立自動助理連絡人物件：</span><span class="sxs-lookup"><span data-stu-id="418b3-123">The following example creates an auto-attendant Contact object:</span></span>

    New-CsExUmContact -SipAddress sip:exumaa1@fabrikam.com -RegistrarPool RedmondPool.litwareinc.com -OU "OU=ExUmContacts,DC=litwareinc,DC=com" -DisplayNumber 2065559876 -AutoAttendant $True

<span data-ttu-id="418b3-124">這個範例會使用 SIP 位址 sip:exumaa1@fabrikam.com 來建立新的 Exchange UM 連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="418b3-124">This example creates a new Exchange UM Contact object with the SIP address sip:exumaa1@fabrikam.com.</span></span> <span data-ttu-id="418b3-125">Lync Server 2013 註冊機構服務正在執行的池名稱是 RedmondPool.litwareinc.com。</span><span class="sxs-lookup"><span data-stu-id="418b3-125">The name of the pool where the Lync Server 2013 Registrar service is running is RedmondPool.litwareinc.com.</span></span> <span data-ttu-id="418b3-126">儲存此資訊的 Active Directory 組織單位為 OU = ExUmContacts、DC = litwareinc、DC = com。</span><span class="sxs-lookup"><span data-stu-id="418b3-126">The Active Directory organizational unit where this information will be stored is OU=ExUmContacts,DC=litwareinc,DC=com.</span></span> <span data-ttu-id="418b3-127">連絡人物件的電話號碼是2065554567。</span><span class="sxs-lookup"><span data-stu-id="418b3-127">The phone number of the Contact object is 2065554567.</span></span> <span data-ttu-id="418b3-128">[選用自動調整] $True 參數會指定此物件是自動助理連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="418b3-128">The optional -AutoAttendant $True parameter specifies that this object is an auto-attendant Contact object.</span></span> <span data-ttu-id="418b3-129">將-自動助理參數設定為 False （預設值），會指定訂閱者存取連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="418b3-129">Setting the -AutoAttendant parameter to False (the default) specifies a subscriber access Contact object.</span></span>

<span data-ttu-id="418b3-130">如需有關新的 CsExUmContact 和 CsExUmContact Cmdlet 的詳細資訊，請參閱 Lync Server 管理命令介面檔。</span><span class="sxs-lookup"><span data-stu-id="418b3-130">For details about the New-CsExUmContact and Set-CsExUmContact cmdlets, see the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

