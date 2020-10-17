---
title: Lync Server 2013：建立主控 Exchange UM 的連絡人物件
description: Lync Server 2013：建立主控 Exchange UM 的連絡人物件。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create contact objects for hosted Exchange UM
ms:assetid: a39be52f-488a-4523-ad5f-ce1f0d681959
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412765(v=OCS.15)
ms:contentKeyID: 48185045
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c9760e2a39b5182f9b5194e364e059bddc6a63d2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562299"
---
# <a name="create-contact-objects-for-hosted-exchange-um-in-lync-server-2013"></a><span data-ttu-id="517c1-103">在 Lync Server 2013 中建立主控 Exchange UM 的連絡人物件</span><span class="sxs-lookup"><span data-stu-id="517c1-103">Create contact objects for hosted Exchange UM in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="517c1-104">_**主題上次修改日期：** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="517c1-104">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="517c1-105">下列程式說明如何建立自動語音應答 (AA) 或訂閱者存取 (SA) 連絡人物件，以供主控 Exchange 整合通訊 (UM) 。</span><span class="sxs-lookup"><span data-stu-id="517c1-105">The following procedure explains how to create Auto Attendant (AA) or Subscriber Access (SA) contact objects for hosted Exchange Unified Messaging (UM).</span></span>

<span data-ttu-id="517c1-106">如需詳細資訊，請參閱規劃檔中的 [主控 Exchange 連絡人物件管理（Lync Server 2013](lync-server-2013-hosted-exchange-contact-object-management.md) ）。</span><span class="sxs-lookup"><span data-stu-id="517c1-106">For details, see [Hosted Exchange Contact object management in Lync Server 2013](lync-server-2013-hosted-exchange-contact-object-management.md) in the Planning documentation.</span></span>

<span data-ttu-id="517c1-107">如需設定連絡人物件的詳細資訊，請參閱 Lync Server 管理命令介面檔中的下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="517c1-107">For details about configuring contact objects, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="517c1-108">New-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="517c1-108">New-CsExUmContact</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsExUmContact)

  - [<span data-ttu-id="517c1-109">Set-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="517c1-109">Set-CsExUmContact</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsExUmContact)

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="517c1-110">在 Lync Server 2013 的連絡人物件可供主控 Exchange UM 啟用之前，必須先部署適用于這些物件的主控語音信箱原則。</span><span class="sxs-lookup"><span data-stu-id="517c1-110">Before Lync Server 2013 contact objects can be enabled for hosted Exchange UM, a hosted voice mail policy that applies to them must be deployed.</span></span> <span data-ttu-id="517c1-111">如需詳細資訊，請參閱 <A href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013 中的主控語音信箱原則</A>。</span><span class="sxs-lookup"><span data-stu-id="517c1-111">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-aa-or-sa-contact-objects-for-hosted-exchange-um"></a><span data-ttu-id="517c1-112">為主控 Exchange UM 建立 AA 或 SA 連絡人物件</span><span class="sxs-lookup"><span data-stu-id="517c1-112">To create AA or SA contact objects for hosted Exchange UM</span></span>

1.  <span data-ttu-id="517c1-113">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="517c1-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="517c1-114">執行 New-CsExUmContact Cmdlet，以建立部署所需的任何連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="517c1-114">Run the New-CsExUmContact cmdlet to create any contact objects required for your deployment.</span></span> <span data-ttu-id="517c1-115">例如，執行下列程式以建立 AA 及 SA 連絡人物件：</span><span class="sxs-lookup"><span data-stu-id="517c1-115">For example, run the following to create an AA and an SA contact object:</span></span>
    
       ```powershell
        New-CsExUmContact -SipAddress "sip:exumaa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101" -AutoAttendant $True
       ```
    
       ```powershell
        New-CsExUmContact -SipAddress "sip:exumsa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101"
       ```
    
    <span data-ttu-id="517c1-116">這些範例會設定下列參數：</span><span class="sxs-lookup"><span data-stu-id="517c1-116">These examples set the following parameters:</span></span>
    
      - <span data-ttu-id="517c1-117">**SipAddress** 會指定連絡人物件的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="517c1-117">**SipAddress** specifies the SIP address of the contact object.</span></span> <span data-ttu-id="517c1-118">這必須是尚未用來設定 Active Directory 網域服務中的使用者或連絡人物件的位址。</span><span class="sxs-lookup"><span data-stu-id="517c1-118">This must be an address that has not already been used to configure a user or contact object in Active Directory Domain Services.</span></span> <span data-ttu-id="517c1-119">此值必須是 "sip：" 的格式， \<*SIP address*\> 如先前的範例所示。</span><span class="sxs-lookup"><span data-stu-id="517c1-119">This value must be in the format “sip:\<*SIP address*\>“ as shown in the previous examples.</span></span>
    
      - <span data-ttu-id="517c1-120">**RegistrarPool** 會指定執行註冊服務之集區的完整功能變數名稱 (FQDN) 。</span><span class="sxs-lookup"><span data-stu-id="517c1-120">**RegistrarPool** specifies the fully qualified domain name (FQDN) of the pool on which the Registrar service is running.</span></span>
        
        <div class=" ">
        

        > [!NOTE]  
        > <span data-ttu-id="517c1-121">在 Lync Server 2013 之前，無法將 Exchange UM 連絡人物件移至屬於 Lync Server 2013 部署一部分的集區。</span><span class="sxs-lookup"><span data-stu-id="517c1-121">Exchange UM contact objects cannot be moved to pools that are part of Lync Server 2013 deployments prior to Lync Server 2013.</span></span>

        
        </div>
    
      - <span data-ttu-id="517c1-122">**OU** 會指定此連絡人物件所在的 Active Directory 組織單位。</span><span class="sxs-lookup"><span data-stu-id="517c1-122">**OU** specifies the Active Directory organizational unit where this contact object will be located.</span></span>
    
      - <span data-ttu-id="517c1-123">**DisplayNumber** 會指定連絡人物件的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="517c1-123">**DisplayNumber** specifies the telephone number of the contact object.</span></span> <span data-ttu-id="517c1-124">每個連絡人物件的電話號碼都必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="517c1-124">The phone number for each contact object must be unique.</span></span>
    
      - <span data-ttu-id="517c1-125">**AutoAttendant** 會指定連絡人物件是否為自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="517c1-125">**AutoAttendant** specifies whether the Contact object is an Auto Attendant.</span></span> <span data-ttu-id="517c1-126">自動語音應答提供一組語音提示，讓來電者能夠流覽電話系統，並抵達他們想要聯絡的方。</span><span class="sxs-lookup"><span data-stu-id="517c1-126">Auto Attendant provides a set of voice prompts that allow callers to navigate the phone system and reach the party that they want to contact.</span></span> <span data-ttu-id="517c1-127">值為 **False** (此參數的預設) 會指出訂戶存取連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="517c1-127">A value of **False** (the default) for this parameter indicates a Subscriber Access contact object.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

