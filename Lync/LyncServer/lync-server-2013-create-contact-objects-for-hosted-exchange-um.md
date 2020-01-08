---
title: Lync Server 2013：建立主控 Exchange UM 的聯絡人物件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create contact objects for hosted Exchange UM
ms:assetid: a39be52f-488a-4523-ad5f-ce1f0d681959
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412765(v=OCS.15)
ms:contentKeyID: 48185045
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53d5bdfe3b341f534a3e8066fe85be5e93b0a7f7
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40974490"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-contact-objects-for-hosted-exchange-um-in-lync-server-2013"></a><span data-ttu-id="36f96-102">在 Lync Server 2013 中建立主控 Exchange UM 的聯絡人物件</span><span class="sxs-lookup"><span data-stu-id="36f96-102">Create contact objects for hosted Exchange UM in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36f96-103">_**主題上次修改日期：** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="36f96-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="36f96-104">下列程式說明如何針對託管 Exchange 整合通訊（UM）建立自動語音應答（AA）或訂閱者存取（SA）連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="36f96-104">The following procedure explains how to create Auto Attendant (AA) or Subscriber Access (SA) contact objects for hosted Exchange Unified Messaging (UM).</span></span>

<span data-ttu-id="36f96-105">如需詳細資訊，請參閱規劃檔中的[Lync Server 2013 中託管的 Exchange 連絡人物件管理](lync-server-2013-hosted-exchange-contact-object-management.md)。</span><span class="sxs-lookup"><span data-stu-id="36f96-105">For details, see [Hosted Exchange Contact object management in Lync Server 2013](lync-server-2013-hosted-exchange-contact-object-management.md) in the Planning documentation.</span></span>

<span data-ttu-id="36f96-106">如需有關設定連絡人物件的詳細資訊，請參閱適用于下列 Cmdlet 的 Lync Server 管理命令介面檔：</span><span class="sxs-lookup"><span data-stu-id="36f96-106">For details about configuring contact objects, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="36f96-107">新-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="36f96-107">New-CsExUmContact</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsExUmContact)

  - [<span data-ttu-id="36f96-108">Set-CsExUmContact</span><span class="sxs-lookup"><span data-stu-id="36f96-108">Set-CsExUmContact</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsExUmContact)

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="36f96-109">在 Lync Server 2013 連絡人物件可供託管 Exchange UM 使用之前，必須先部署適用于它們的託管語音信箱原則。</span><span class="sxs-lookup"><span data-stu-id="36f96-109">Before Lync Server 2013 contact objects can be enabled for hosted Exchange UM, a hosted voice mail policy that applies to them must be deployed.</span></span> <span data-ttu-id="36f96-110">如需詳細資訊，請參閱<A href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013 中託管的語音信箱原則</A>。</span><span class="sxs-lookup"><span data-stu-id="36f96-110">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-aa-or-sa-contact-objects-for-hosted-exchange-um"></a><span data-ttu-id="36f96-111">若要為託管 Exchange UM 建立 AA 或 SA 連絡人物件</span><span class="sxs-lookup"><span data-stu-id="36f96-111">To create AA or SA contact objects for hosted Exchange UM</span></span>

1.  <span data-ttu-id="36f96-112">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="36f96-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="36f96-113">執行新的 CsExUmContact Cmdlet，以建立您部署所需的任何連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="36f96-113">Run the New-CsExUmContact cmdlet to create any contact objects required for your deployment.</span></span> <span data-ttu-id="36f96-114">例如，請執行下列動作來建立 AA 與 SA 連絡人物件：</span><span class="sxs-lookup"><span data-stu-id="36f96-114">For example, run the following to create an AA and an SA contact object:</span></span>
    
       ```powershell
        New-CsExUmContact -SipAddress "sip:exumaa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101" -AutoAttendant $True
       ```
    
       ```powershell
        New-CsExUmContact -SipAddress "sip:exumsa1@fabrikam.com" -RegistrarPool "RedmondPool.litwareinc.com" -OU "HostedExUM Integration" -DisplayNumber "+14255550101"
       ```
    
    <span data-ttu-id="36f96-115">這些範例會設定下列參數：</span><span class="sxs-lookup"><span data-stu-id="36f96-115">These examples set the following parameters:</span></span>
    
      - <span data-ttu-id="36f96-116">**SipAddress**指定連絡人物件的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="36f96-116">**SipAddress** specifies the SIP address of the contact object.</span></span> <span data-ttu-id="36f96-117">此位址必須是尚未用來設定 Active Directory 網域服務中的使用者或連絡人物件的位址。</span><span class="sxs-lookup"><span data-stu-id="36f96-117">This must be an address that has not already been used to configure a user or contact object in Active Directory Domain Services.</span></span> <span data-ttu-id="36f96-118">此值必須是「sip：\<*sip 位址*\>」格式，如先前的範例所示。</span><span class="sxs-lookup"><span data-stu-id="36f96-118">This value must be in the format “sip:\<*SIP address*\>“ as shown in the previous examples.</span></span>
    
      - <span data-ttu-id="36f96-119">**RegistrarPool**指定運行註冊服務之池的完整功能變數名稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="36f96-119">**RegistrarPool** specifies the fully qualified domain name (FQDN) of the pool on which the Registrar service is running.</span></span>
        
        <div class=" ">
        

        > [!NOTE]  
        > <span data-ttu-id="36f96-120">在 Lync Server 2013 之前，無法將 Exchange UM 連絡人物件移到屬於 Lync Server 2013 部署的 pool。</span><span class="sxs-lookup"><span data-stu-id="36f96-120">Exchange UM contact objects cannot be moved to pools that are part of Lync Server 2013 deployments prior to Lync Server 2013.</span></span>

        
        </div>
    
      - <span data-ttu-id="36f96-121">**OU** ：指定此連絡人物件將位於哪個 Active Directory 組織單位。</span><span class="sxs-lookup"><span data-stu-id="36f96-121">**OU** specifies the Active Directory organizational unit where this contact object will be located.</span></span>
    
      - <span data-ttu-id="36f96-122">**DisplayNumber**指定連絡人物件的電話號碼。</span><span class="sxs-lookup"><span data-stu-id="36f96-122">**DisplayNumber** specifies the telephone number of the contact object.</span></span> <span data-ttu-id="36f96-123">每個連絡人物件的電話號碼都必須是唯一的。</span><span class="sxs-lookup"><span data-stu-id="36f96-123">The phone number for each contact object must be unique.</span></span>
    
      - <span data-ttu-id="36f96-124">[自動**助理**] 可指定連絡人物件是否為自動語音應答。</span><span class="sxs-lookup"><span data-stu-id="36f96-124">**AutoAttendant** specifies whether the Contact object is an Auto Attendant.</span></span> <span data-ttu-id="36f96-125">自動語音應答會提供一組語音提示，讓呼叫者流覽電話系統，並到達他們想要聯絡的對方。</span><span class="sxs-lookup"><span data-stu-id="36f96-125">Auto Attendant provides a set of voice prompts that allow callers to navigate the phone system and reach the party that they want to contact.</span></span> <span data-ttu-id="36f96-126">此參數的**False**值（預設值）表示訂閱者存取連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="36f96-126">A value of **False** (the default) for this parameter indicates a Subscriber Access contact object.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

