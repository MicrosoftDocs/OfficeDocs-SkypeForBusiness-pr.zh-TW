---
title: Lync Server 2013：建立或修改公用的區域電話連絡人物件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a common area phone Contact object
ms:assetid: eec33ad1-e4f2-49b2-91d6-d5a9d2e1714b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994083(v=OCS.15)
ms:contentKeyID: 51803995
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee1345477178d7991083332e809de3f764be4c3a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976048"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-common-area-phone-contact-object-in-lync-server-2013"></a><span data-ttu-id="d9ee9-102">在 Lync Server 2013 中建立或修改常見的區域電話連絡人物件</span><span class="sxs-lookup"><span data-stu-id="d9ee9-102">Create or modify a common area phone Contact object in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9ee9-103">_**主題上次修改日期：** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="d9ee9-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="d9ee9-104">若要為您的所有常見區域手機建立 Active Directory 網域服務連絡人物件，請使用**CsCommonAreaPhone** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d9ee9-104">To create Active Directory Domain Services contact objects for all your common area phones, use the **New-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="d9ee9-105">這個 Cmdlet 可以建立新的連絡人物件以搭配普通的區域電話使用，或將現有的連絡人物件與新的通用區域手機建立關聯。</span><span class="sxs-lookup"><span data-stu-id="d9ee9-105">This cmdlet can either create new contact objects for use with common area phones, or it can associate existing contact objects with a new common area phone.</span></span> <span data-ttu-id="d9ee9-106">若要修改與常見區域手機相關聯之連絡人物件的屬性，請使用**CsCommonAreaPhone** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d9ee9-106">To modify the properties of the contact objects associated with common area phones, use the **Set-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="d9ee9-107">[**設定 CsCommonAreaPhone** ] 的選用參數可讓您變更專案，例如連絡人的 Active Directory 顯示名稱或與手機相關聯的行統一資源識別項（URI），並啟用和停用 Lync Server 所用的帳戶。</span><span class="sxs-lookup"><span data-stu-id="d9ee9-107">Optional parameters for **Set-CsCommonAreaPhone** enable you to change items, such as the contact’s Active Directory display name or the line Uniform Resource Identifier (URI) associated with the phone, and enable and disable the account for use with Lync Server.</span></span> <span data-ttu-id="d9ee9-108">如需所有可用修改的詳細資料，請參閱[設定 CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone)的參數區段。</span><span class="sxs-lookup"><span data-stu-id="d9ee9-108">For details about all the available modifications, see the Parameters section at [Set-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone).</span></span> <span data-ttu-id="d9ee9-109">如需有關**新的 CsCommonAreaPhone**參數的詳細資訊，請參閱[CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone)。</span><span class="sxs-lookup"><span data-stu-id="d9ee9-109">For details about **New-CsCommonAreaPhone** parameters, see [New-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone).</span></span>

<span data-ttu-id="d9ee9-110">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 遠端會話執行這兩個 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d9ee9-110">You can run these two cmdlets from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="d9ee9-111">如需使用遠端 Windows PowerShell 連線至 Lync Server 的詳細資料，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="d9ee9-111">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="creating-a-common-area-phone-contact-object"></a><span data-ttu-id="d9ee9-112">建立共同的區域電話連絡人物件</span><span class="sxs-lookup"><span data-stu-id="d9ee9-112">Creating a common area phone contact object</span></span>

  - <span data-ttu-id="d9ee9-113">若要建立新的通用區域電話連絡人物件，請使用**CsCommonAreaPhone** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d9ee9-113">To create a new common area phone contact object, use the **New-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="d9ee9-114">在建立連絡人物件時，您必須至少提供下列資訊：</span><span class="sxs-lookup"><span data-stu-id="d9ee9-114">At a minimum, you must supply the following information when creating a contact object:</span></span>
    
      - <span data-ttu-id="d9ee9-115">**LineUri**：指派給常見區域電話的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="d9ee9-115">**LineUri**: The telephone number assigned to the common area phone.</span></span> <span data-ttu-id="d9ee9-116">請注意，在指定電話號碼時，您必須使用 E. 164 格式。</span><span class="sxs-lookup"><span data-stu-id="d9ee9-116">Note that you must use the E.164 format when specifying the phone number.</span></span>
    
      - <span data-ttu-id="d9ee9-117">**RegistrarPool**：將主持連絡人物件的註冊機構池的完整功能變數名稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="d9ee9-117">**RegistrarPool**: The fully qualified domain name (FQDN) of the Registrar pool that will host the contact object.</span></span>
    
      - <span data-ttu-id="d9ee9-118">**OU**：將建立連絡人物件之 Active Directory 容器的判別名。</span><span class="sxs-lookup"><span data-stu-id="d9ee9-118">**OU**: Distinguished name of the Active Directory container where the contact object will be created.</span></span>
    
    <span data-ttu-id="d9ee9-119">我們也建議您提供 Active Directory 網域服務顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="d9ee9-119">We also recommend that you provide an Active Directory Domain Services display name.</span></span> <span data-ttu-id="d9ee9-120">否則，您將需要使用 GUID 來指定電話身分識別。</span><span class="sxs-lookup"><span data-stu-id="d9ee9-120">Otherwise, you will need to use a GUID to specify the phone Identity.</span></span> <span data-ttu-id="d9ee9-121">例如：</span><span class="sxs-lookup"><span data-stu-id="d9ee9-121">For example:</span></span>
    
        New-CsCommonAreaPhone -LineUri "tel:+12065551219" -RegistrarPool "atl-cs-001.litwareinc.com" -OU "OU=Phones,dc=litwareinc,dc=com" -DisplayName "Lobby"

</div>

<div>

## <a name="modifying-a-common-area-phone-contact-object"></a><span data-ttu-id="d9ee9-122">修改常見的區域電話連絡人物件</span><span class="sxs-lookup"><span data-stu-id="d9ee9-122">Modifying a common area phone contact object</span></span>

  - <span data-ttu-id="d9ee9-123">若要修改現有常見區域電話的屬性，請使用**CsCommonAreaPhone** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d9ee9-123">To modify the properties of an existing common area phone, contact object use the **Set-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="d9ee9-124">例如，這個命令會使用 DisplayName 大廳來設定常見區域手機的 SIP 位址：</span><span class="sxs-lookup"><span data-stu-id="d9ee9-124">For example, this command configures the SIP address for the common area phone with the DisplayName Lobby:</span></span>
    
        Set-CsCommonAreaPhone -Identity "Lobby" -SipAddress "sip:lobby@litwareinc.com"

</div>

<span data-ttu-id="d9ee9-125">如需詳細資訊，請參閱[新版 CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone) Cmdlet 和[CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="d9ee9-125">For details, see the Help topics for the [New-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone) cmdlet and the [Set-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

