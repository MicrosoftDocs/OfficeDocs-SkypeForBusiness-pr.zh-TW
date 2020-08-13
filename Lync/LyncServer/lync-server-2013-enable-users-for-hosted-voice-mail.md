---
title: Lync Server 2013：針對主控的語音信箱啟用使用者
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable users for hosted voice mail
ms:assetid: fa559f8f-ef99-43a1-b580-9e998b95efb8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413062(v=OCS.15)
ms:contentKeyID: 48185919
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 836edd026e6b80404b9a85a3d5a0f53fa2ba574a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187806"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-users-for-hosted-voice-mail-in-lync-server-2013"></a><span data-ttu-id="827c1-102">在 Lync Server 2013 中啟用使用者的主控語音信箱功能</span><span class="sxs-lookup"><span data-stu-id="827c1-102">Enable users for hosted voice mail in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="827c1-103">_**主題上次修改日期：** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="827c1-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="827c1-104">請遵循程式，在主控 Exchange 整合通訊 (UM) 服務上啟用語音信箱的 Lync Server 2013 使用者。</span><span class="sxs-lookup"><span data-stu-id="827c1-104">Follow the procedure to enable Lync Server 2013 users for voice mail on a hosted Exchange Unified Messaging (UM) service.</span></span>

<span data-ttu-id="827c1-105">如需詳細資訊，請參閱規劃檔中的[主控 Exchange 使用者管理（Lync Server 2013](lync-server-2013-hosted-exchange-user-management.md) ）。</span><span class="sxs-lookup"><span data-stu-id="827c1-105">For details, see [Hosted Exchange user management in Lync Server 2013](lync-server-2013-hosted-exchange-user-management.md) in the Planning documentation.</span></span>

<span data-ttu-id="827c1-106">如需[Set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) Cmdlet 的詳細資訊，請參閱 Lync Server 管理命令介面檔。</span><span class="sxs-lookup"><span data-stu-id="827c1-106">For details about the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) cmdlet, see the Lync Server Management Shell documentation.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="827c1-107">在 Lync Server 2013 使用者可以啟用裝載的語音信箱之前，必須先部署套用至使用者帳戶的主控語音信箱原則。</span><span class="sxs-lookup"><span data-stu-id="827c1-107">Before a Lync Server 2013 user can be enabled for hosted voice mail, a hosted voice mail policy that applies to their user account must be deployed.</span></span> <span data-ttu-id="827c1-108">如需詳細資訊，請參閱<A href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013 中的主控語音信箱原則</A>。</span><span class="sxs-lookup"><span data-stu-id="827c1-108">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-users-for-hosted-voice-mail"></a><span data-ttu-id="827c1-109">啟用使用者的主控語音信箱</span><span class="sxs-lookup"><span data-stu-id="827c1-109">To enable users for hosted voice mail</span></span>

1.  <span data-ttu-id="827c1-110">啟動 Lync Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="827c1-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="827c1-111">執行 Set-CsUser Cmdlet 以設定主控語音信箱的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="827c1-111">Run the Set-CsUser cmdlet to configure the user account for hosted voice mail.</span></span> <span data-ttu-id="827c1-112">例如，執行：</span><span class="sxs-lookup"><span data-stu-id="827c1-112">For example, run:</span></span>
    
        Set-CsUser -HostedVoiceMail $True -Identity "contoso\kenmyer"
    
    <span data-ttu-id="827c1-113">上述範例會設定下列參數：</span><span class="sxs-lookup"><span data-stu-id="827c1-113">The preceding example sets the following parameters:</span></span>
    
      - <span data-ttu-id="827c1-114">**HostedVoiceMail**可讓使用者的語音信箱呼叫路由傳送至主控 Exchange UM。</span><span class="sxs-lookup"><span data-stu-id="827c1-114">**HostedVoiceMail** enables a user’s voice mail calls to be routed to hosted Exchange UM.</span></span> <span data-ttu-id="827c1-115">它也會向 Microsoft Lync 2013 發出語音訊息，以發光「呼叫語音信箱」指示器。</span><span class="sxs-lookup"><span data-stu-id="827c1-115">It also signals Microsoft Lync 2013 to light up the “call voice mail” indicator.</span></span>
    
      - <span data-ttu-id="827c1-116">**Identity**指定要修改的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="827c1-116">**Identity** specifies the user account to be modified.</span></span> <span data-ttu-id="827c1-117">您可以使用下列任何格式指定 Identity 值：</span><span class="sxs-lookup"><span data-stu-id="827c1-117">The Identity value can be specified using any of the following formats:</span></span>
        
          - <span data-ttu-id="827c1-118">使用者的 SIP 位址</span><span class="sxs-lookup"><span data-stu-id="827c1-118">The user's SIP address</span></span>
        
          - <span data-ttu-id="827c1-119">使用者的 Active Directory 使用者主體名稱</span><span class="sxs-lookup"><span data-stu-id="827c1-119">The user's Active Directory User-Principal-Name</span></span>
        
          - <span data-ttu-id="827c1-120">使用者的網域 \\ 登入名稱 (例如，contoso \\ kenmyer) </span><span class="sxs-lookup"><span data-stu-id="827c1-120">The user's domain\\logon name (for example, contoso\\kenmyer)</span></span>
        
          - <span data-ttu-id="827c1-121">使用者的 Active Directory 網域服務顯示名稱 (例如，Ken Myer) 。</span><span class="sxs-lookup"><span data-stu-id="827c1-121">The user's Active Directory Domain Services Display-Name (for example, Ken Myer).</span></span> <span data-ttu-id="827c1-122">如果使用顯示名稱做為 Identity 值，您可以使用星號 (\*) 萬用字元。</span><span class="sxs-lookup"><span data-stu-id="827c1-122">If using the Display-Name as the Identity value, you can use the asterisk (\*) wildcard character.</span></span> <span data-ttu-id="827c1-123">例如，身分識別 " \* smith" 會傳回顯示名稱結尾為字串值 "Smith" 的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="827c1-123">For example, the Identity "\* Smith" returns all the users who have a Display-Name that ends with the string value "Smith".</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="827c1-124">使用者的 Active Directory SAM 帳戶名稱不能做為身分識別值，因為 SAM 帳戶名稱在樹系中不一定是唯一的。</span><span class="sxs-lookup"><span data-stu-id="827c1-124">The user’s Active Directory SAM-Account-Name cannot be used as the Identity value because the SAM-Account-Name is not necessarily unique in the forest.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

