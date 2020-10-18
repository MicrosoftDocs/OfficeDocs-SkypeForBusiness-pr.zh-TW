---
title: Lync Server 2013：建立或修改公共區域電話連絡人物件
description: Lync Server 2013：建立或修改通用區域電話連絡人物件。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a common area phone Contact object
ms:assetid: eec33ad1-e4f2-49b2-91d6-d5a9d2e1714b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994083(v=OCS.15)
ms:contentKeyID: 51803995
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: adc5ede23f495a63b2d556b556817d4171a08723
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578229"
---
# <a name="create-or-modify-a-common-area-phone-contact-object-in-lync-server-2013"></a><span data-ttu-id="ca000-103">在 Lync Server 2013 中建立或修改公共區域電話連絡人物件</span><span class="sxs-lookup"><span data-stu-id="ca000-103">Create or modify a common area phone Contact object in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca000-104">_**主題上次修改日期：** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="ca000-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="ca000-105">若要為您的所有公共區域電話建立 Active Directory 網域服務連絡人物件，請使用 **New-CsCommonAreaPhone** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ca000-105">To create Active Directory Domain Services contact objects for all your common area phones, use the **New-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="ca000-106">這個指令程式可以建立新的連絡人物件，以與公共區域電話搭配使用，也可以將現有的連絡人物件與新的通用區域電話產生關聯。</span><span class="sxs-lookup"><span data-stu-id="ca000-106">This cmdlet can either create new contact objects for use with common area phones, or it can associate existing contact objects with a new common area phone.</span></span> <span data-ttu-id="ca000-107">若要修改與公共區域電話相關聯之連絡人物件的屬性，請使用 **CsCommonAreaPhone 指令程式** 。</span><span class="sxs-lookup"><span data-stu-id="ca000-107">To modify the properties of the contact objects associated with common area phones, use the **Set-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="ca000-108">**Set-CsCommonAreaPhone**的選用參數可讓您變更專案，例如連絡人的 Active Directory 顯示名稱或行統一資源識別項 (URI) 與電話相關聯，並啟用及停用與 Lync Server 搭配使用的帳戶。</span><span class="sxs-lookup"><span data-stu-id="ca000-108">Optional parameters for **Set-CsCommonAreaPhone** enable you to change items, such as the contact’s Active Directory display name or the line Uniform Resource Identifier (URI) associated with the phone, and enable and disable the account for use with Lync Server.</span></span> <span data-ttu-id="ca000-109">如需所有可用修改的詳細資訊，請參閱 Parameters 區段 [CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone)。</span><span class="sxs-lookup"><span data-stu-id="ca000-109">For details about all the available modifications, see the Parameters section at [Set-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone).</span></span> <span data-ttu-id="ca000-110">如需 **New-CsCommonAreaPhone** 參數的詳細資訊，請參閱 [New-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone)。</span><span class="sxs-lookup"><span data-stu-id="ca000-110">For details about **New-CsCommonAreaPhone** parameters, see [New-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone).</span></span>

<span data-ttu-id="ca000-111">您可以從 Lync Server 2013 管理命令介面或從 Windows PowerShell 的遠端會話中執行這兩個 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ca000-111">You can run these two cmdlets from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="ca000-112">如需使用遠端 Windows PowerShell 連接至 Lync Server 的詳細資訊，請參閱 Lync Server Windows PowerShell 博客文章「快速入門：使用遠端 PowerShell 管理 Microsoft Lync Server 2010」 at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="ca000-112">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="creating-a-common-area-phone-contact-object"></a><span data-ttu-id="ca000-113">建立公共區域電話連絡人物件</span><span class="sxs-lookup"><span data-stu-id="ca000-113">Creating a common area phone contact object</span></span>

  - <span data-ttu-id="ca000-114">若要建立新的公共區域電話連絡人物件，請使用 **New-CsCommonAreaPhone** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ca000-114">To create a new common area phone contact object, use the **New-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="ca000-115">在建立連絡人物件時，至少必須提供下列資訊：</span><span class="sxs-lookup"><span data-stu-id="ca000-115">At a minimum, you must supply the following information when creating a contact object:</span></span>
    
      - <span data-ttu-id="ca000-116">**LineUri**：指派給公共區域電話的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="ca000-116">**LineUri**: The telephone number assigned to the common area phone.</span></span> <span data-ttu-id="ca000-117">請注意，指定電話號碼時，必須使用 e.164 格式。</span><span class="sxs-lookup"><span data-stu-id="ca000-117">Note that you must use the E.164 format when specifying the phone number.</span></span>
    
      - <span data-ttu-id="ca000-118">**RegistrarPool**：將主控 contact 物件之註冊集區的完整功能變數名稱 (FQDN) 。</span><span class="sxs-lookup"><span data-stu-id="ca000-118">**RegistrarPool**: The fully qualified domain name (FQDN) of the Registrar pool that will host the contact object.</span></span>
    
      - <span data-ttu-id="ca000-119">**OU**：將建立連絡人物件的 Active Directory 容器的辨別名稱。</span><span class="sxs-lookup"><span data-stu-id="ca000-119">**OU**: Distinguished name of the Active Directory container where the contact object will be created.</span></span>
    
    <span data-ttu-id="ca000-120">我們也建議您提供 Active Directory 網域服務顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="ca000-120">We also recommend that you provide an Active Directory Domain Services display name.</span></span> <span data-ttu-id="ca000-121">否則，您必須使用 GUID 來指定電話身分識別。</span><span class="sxs-lookup"><span data-stu-id="ca000-121">Otherwise, you will need to use a GUID to specify the phone Identity.</span></span> <span data-ttu-id="ca000-122">例如：</span><span class="sxs-lookup"><span data-stu-id="ca000-122">For example:</span></span>
    
        New-CsCommonAreaPhone -LineUri "tel:+12065551219" -RegistrarPool "atl-cs-001.litwareinc.com" -OU "OU=Phones,dc=litwareinc,dc=com" -DisplayName "Lobby"

</div>

<div>

## <a name="modifying-a-common-area-phone-contact-object"></a><span data-ttu-id="ca000-123">修改公共區域電話連絡人物件</span><span class="sxs-lookup"><span data-stu-id="ca000-123">Modifying a common area phone contact object</span></span>

  - <span data-ttu-id="ca000-124">若要修改現有的公共區域電話的屬性，contact 物件使用 **CsCommonAreaPhone 指令程式** 。</span><span class="sxs-lookup"><span data-stu-id="ca000-124">To modify the properties of an existing common area phone, contact object use the **Set-CsCommonAreaPhone** cmdlet.</span></span> <span data-ttu-id="ca000-125">例如，此命令會使用 DisplayName 會議廳設定常見區域電話的 SIP 位址：</span><span class="sxs-lookup"><span data-stu-id="ca000-125">For example, this command configures the SIP address for the common area phone with the DisplayName Lobby:</span></span>
    
        Set-CsCommonAreaPhone -Identity "Lobby" -SipAddress "sip:lobby@litwareinc.com"

</div>

<span data-ttu-id="ca000-126">如需詳細資訊，請參閱 [New-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone) Cmdlet 和 [CsCommonAreaPhone 指令程式](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone) 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="ca000-126">For details, see the Help topics for the [New-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone) cmdlet and the [Set-CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

