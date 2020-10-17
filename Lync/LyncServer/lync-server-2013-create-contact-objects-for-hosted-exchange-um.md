---
title: Lync Server 2013：建立主控 Exchange UM 的連絡人物件
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
ms.openlocfilehash: 051b7f483ec3e3a59d5025c670b63b97765016b5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532300"
---
# <a name="create-contact-objects-for-hosted-exchange-um-in-lync-server-2013"></a><span data-ttu-id="deaf9-102">在 Lync Server 2013 中建立主控 Exchange UM 的連絡人物件</span><span class="sxs-lookup"><span data-stu-id="deaf9-102">Create contact objects for hosted Exchange UM in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="deaf9-103">_**主題上次修改日期：** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="deaf9-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="deaf9-104">下列程式說明如何建立自動語音應答 (AA) 或訂閱者存取 (SA) 連絡人物件，以供主控 Exchange 整合通訊 (UM) 。</span><span class="sxs-lookup"><span data-stu-id="deaf9-104">The following procedure explains how to create Auto Attendant (AA) or Subscriber Access (SA) contact objects for hosted Exchange Unified Messaging (UM).</span></span>

<span data-ttu-id="deaf9-105">如需詳細資訊，請參閱規劃檔中的 [主控 Exchange 連絡人物件管理（Lync Server 2013](lync-server-2013-hosted-exchange-contact-object-management.md) ）。</span><span class="sxs-lookup"><span data-stu-id="deaf9-105">For details, see [Hosted Exchange Contact object management in Lync Server 2013](lync-server-2013-hosted-exchange-contact-object-management.md) in the Planning documentation.</span></span>

<span data-ttu-id="deaf9-106">如需設定連絡人物件的詳細資訊，請參閱 Lync Server 管理命令介面檔中的下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="deaf9-106">For details about configuring contact objects, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="deaf9-107">New-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="deaf9-107">New-CsExUmContact</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsExUmContact)

  - [<span data-ttu-id="deaf9-108">Set-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="deaf9-108">Set-CsExUmContact</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsExUmContact)

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="deaf9-109">在 Lync Server 2013 的連絡人物件可供主控 Exchange UM 啟用之前，必須先部署適用于這些物件的主控語音信箱原則。</span><span class="sxs-lookup"><span data-stu-id="deaf9-109">Before Lync Server 2013 contact objects can be enabled for hosted Exchange UM, a hosted voice mail policy that applies to them must be deployed.</span></span> <span data-ttu-id="deaf9-110">如需詳細資訊，請參閱 <A href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013 中的主控語音信箱原則</A>。</span><span class="sxs-lookup"><span data-stu-id="deaf9-110">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-aa-or-sa-contact-objects-for-hosted-exchange-um"></a><span data-ttu-id="deaf9-111">為主控 Exchange UM 建立 AA 或 SA 連絡人物件</span><span class="sxs-lookup"><span data-stu-id="deaf9-111">To create AA or SA contact objects for hosted Exchange UM</span></span>

1.  <span data-ttu-id="deaf9-112">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="deaf9-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="deaf9-113">執行 New-CsExUmContact Cmdlet，以建立部署所需的任何連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="deaf9-113">Run the New-CsExUmContact cmdlet to create any contact objects required for your deployment.</span></span> <span data-ttu-id="deaf9-114">例如，執行下列程式以建立 AA 及 SA 連絡人物件：</span><span class="sxs-lookup"><span data-stu-id="deaf9-114">For example, run the following to create an AA and an SA contact object:</span></span>
    
       ```powershell
        New-CsExUmContact -SipAddress "sip:exumaa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101" -AutoAttendant $True
       ```
    
       ```powershell
        New-CsExUmContact -SipAddress "sip:exumsa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101"
       ```
    
    <span data-ttu-id="deaf9-115">這些範例會設定下列參數：</span><span class="sxs-lookup"><span data-stu-id="deaf9-115">These examples set the following parameters:</span></span>
    
      - <span data-ttu-id="deaf9-116">**SipAddress** 會指定連絡人物件的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="deaf9-116">**SipAddress** specifies the SIP address of the contact object.</span></span> <span data-ttu-id="deaf9-117">這必須是尚未用來設定 Active Directory 網域服務中的使用者或連絡人物件的位址。</span><span class="sxs-lookup"><span data-stu-id="deaf9-117">This must be an address that has not already been used to configure a user or contact object in Active Directory Domain Services.</span></span> <span data-ttu-id="deaf9-118">此值必須是 "sip：" 的格式， \<*SIP address*\> 如先前的範例所示。</span><span class="sxs-lookup"><span data-stu-id="deaf9-118">This value must be in the format “sip:\<*SIP address*\>“ as shown in the previous examples.</span></span>
    
      - <span data-ttu-id="deaf9-119">**RegistrarPool** 會指定執行註冊服務之集區的完整功能變數名稱 (FQDN) 。</span><span class="sxs-lookup"><span data-stu-id="deaf9-119">**RegistrarPool** specifies the fully qualified domain name (FQDN) of the pool on which the Registrar service is running.</span></span>
        
        <div class=" ">
        

        > [!NOTE]  
        > <span data-ttu-id="deaf9-120">在 Lync Server 2013 之前，無法將 Exchange UM 連絡人物件移至屬於 Lync Server 2013 部署一部分的集區。</span><span class="sxs-lookup"><span data-stu-id="deaf9-120">Exchange UM contact objects cannot be moved to pools that are part of Lync Server 2013 deployments prior to Lync Server 2013.</span></span>

        
        </div>
    
      - <span data-ttu-id="deaf9-121">**OU** 會指定此連絡人物件所在的 Active Directory 組織單位。</span><span class="sxs-lookup"><span data-stu-id="deaf9-121">**OU** specifies the Active Directory organizational unit where this contact object will be located.</span></span>
    
      - <span data-ttu-id="deaf9-122">**DisplayNumber** 會指定連絡人物件的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="deaf9-122">**DisplayNumber** specifies the telephone number of the contact object.</span></span> <span data-ttu-id="deaf9-123">每個連絡人物件的電話號碼都必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="deaf9-123">The phone number for each contact object must be unique.</span></span>
    
      - <span data-ttu-id="deaf9-124">**AutoAttendant** 會指定連絡人物件是否為自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="deaf9-124">**AutoAttendant** specifies whether the Contact object is an Auto Attendant.</span></span> <span data-ttu-id="deaf9-125">自動語音應答提供一組語音提示，讓來電者能夠流覽電話系統，並抵達他們想要聯絡的方。</span><span class="sxs-lookup"><span data-stu-id="deaf9-125">Auto Attendant provides a set of voice prompts that allow callers to navigate the phone system and reach the party that they want to contact.</span></span> <span data-ttu-id="deaf9-126">值為 **False** (此參數的預設) 會指出訂戶存取連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="deaf9-126">A value of **False** (the default) for this parameter indicates a Subscriber Access contact object.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

