---
title: Lync Server 2013：為使用者啟用主控語音信箱
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable users for hosted voice mail
ms:assetid: fa559f8f-ef99-43a1-b580-9e998b95efb8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413062(v=OCS.15)
ms:contentKeyID: 48185919
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45872df26989d8d264ce77406bfbce86f321ccf8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977894"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-users-for-hosted-voice-mail-in-lync-server-2013"></a><span data-ttu-id="f25ff-102">在 Lync Server 2013 中為使用者啟用主控語音信箱</span><span class="sxs-lookup"><span data-stu-id="f25ff-102">Enable users for hosted voice mail in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f25ff-103">_**主題上次修改日期：** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="f25ff-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="f25ff-104">按照程式在託管 Exchange 整合通訊（UM）服務上，為語音信箱啟用 Lync Server 2013 使用者。</span><span class="sxs-lookup"><span data-stu-id="f25ff-104">Follow the procedure to enable Lync Server 2013 users for voice mail on a hosted Exchange Unified Messaging (UM) service.</span></span>

<span data-ttu-id="f25ff-105">如需詳細資訊，請參閱規劃檔中的[Lync Server 2013 中的託管 Exchange 使用者管理](lync-server-2013-hosted-exchange-user-management.md)。</span><span class="sxs-lookup"><span data-stu-id="f25ff-105">For details, see [Hosted Exchange user management in Lync Server 2013](lync-server-2013-hosted-exchange-user-management.md) in the Planning documentation.</span></span>

<span data-ttu-id="f25ff-106">如需[move-csuser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) Cmdlet 的詳細資訊，請參閱 Lync Server 管理命令介面檔。</span><span class="sxs-lookup"><span data-stu-id="f25ff-106">For details about the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) cmdlet, see the Lync Server Management Shell documentation.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f25ff-107">在 Lync Server 2013 使用者可以啟用託管語音信箱之前，必須先部署適用于其使用者帳戶的託管語音信箱原則。</span><span class="sxs-lookup"><span data-stu-id="f25ff-107">Before a Lync Server 2013 user can be enabled for hosted voice mail, a hosted voice mail policy that applies to their user account must be deployed.</span></span> <span data-ttu-id="f25ff-108">如需詳細資訊，請參閱<A href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013 中託管的語音信箱原則</A>。</span><span class="sxs-lookup"><span data-stu-id="f25ff-108">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-users-for-hosted-voice-mail"></a><span data-ttu-id="f25ff-109">允許使用者使用託管的語音信箱</span><span class="sxs-lookup"><span data-stu-id="f25ff-109">To enable users for hosted voice mail</span></span>

1.  <span data-ttu-id="f25ff-110">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="f25ff-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="f25ff-111">執行 Move-csuser Cmdlet 來設定託管語音信箱的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="f25ff-111">Run the Set-CsUser cmdlet to configure the user account for hosted voice mail.</span></span> <span data-ttu-id="f25ff-112">例如，執行：</span><span class="sxs-lookup"><span data-stu-id="f25ff-112">For example, run:</span></span>
    
        Set-CsUser -HostedVoiceMail $True -Identity "contoso\kenmyer"
    
    <span data-ttu-id="f25ff-113">上述範例會設定下列參數：</span><span class="sxs-lookup"><span data-stu-id="f25ff-113">The preceding example sets the following parameters:</span></span>
    
      - <span data-ttu-id="f25ff-114">**HostedVoiceMail**可讓使用者的語音信箱呼叫路由至託管 Exchange UM。</span><span class="sxs-lookup"><span data-stu-id="f25ff-114">**HostedVoiceMail** enables a user’s voice mail calls to be routed to hosted Exchange UM.</span></span> <span data-ttu-id="f25ff-115">它也會通知 Microsoft Lync 2013，以將「撥號語音信箱」指標發亮。</span><span class="sxs-lookup"><span data-stu-id="f25ff-115">It also signals Microsoft Lync 2013 to light up the “call voice mail” indicator.</span></span>
    
      - <span data-ttu-id="f25ff-116">身分**識別**指定要修改的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="f25ff-116">**Identity** specifies the user account to be modified.</span></span> <span data-ttu-id="f25ff-117">身分識別值可以使用下列任何一種格式加以指定：</span><span class="sxs-lookup"><span data-stu-id="f25ff-117">The Identity value can be specified using any of the following formats:</span></span>
        
          - <span data-ttu-id="f25ff-118">使用者的 SIP 位址</span><span class="sxs-lookup"><span data-stu-id="f25ff-118">The user's SIP address</span></span>
        
          - <span data-ttu-id="f25ff-119">使用者的 Active Directory 使用者主要名稱</span><span class="sxs-lookup"><span data-stu-id="f25ff-119">The user's Active Directory User-Principal-Name</span></span>
        
          - <span data-ttu-id="f25ff-120">使用者的網域\\登入名稱（例如 contoso\\kenmyer）</span><span class="sxs-lookup"><span data-stu-id="f25ff-120">The user's domain\\logon name (for example, contoso\\kenmyer)</span></span>
        
          - <span data-ttu-id="f25ff-121">使用者的 Active Directory 網域服務顯示名稱（例如，Ken Myer）。</span><span class="sxs-lookup"><span data-stu-id="f25ff-121">The user's Active Directory Domain Services Display-Name (for example, Ken Myer).</span></span> <span data-ttu-id="f25ff-122">如果使用顯示名稱作為身分識別值，您可以使用星號（\*）萬用字元。</span><span class="sxs-lookup"><span data-stu-id="f25ff-122">If using the Display-Name as the Identity value, you can use the asterisk (\*) wildcard character.</span></span> <span data-ttu-id="f25ff-123">例如，恒等 "\* smith" 會傳回其顯示名稱以字串值 "smith" 結尾的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="f25ff-123">For example, the Identity "\* Smith" returns all the users who have a Display-Name that ends with the string value "Smith".</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="f25ff-124">使用者的 Active Directory SAM-帳戶名稱不能用來做為身分識別值，因為 SAM-帳戶名稱在林中不一定是唯一的。</span><span class="sxs-lookup"><span data-stu-id="f25ff-124">The user’s Active Directory SAM-Account-Name cannot be used as the Identity value because the SAM-Account-Name is not necessarily unique in the forest.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

