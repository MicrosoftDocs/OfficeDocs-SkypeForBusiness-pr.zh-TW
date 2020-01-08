---
title: Lync Server 2013：設定增強的目前狀態隱私權模式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring enhanced presence privacy mode
ms:assetid: e7a6b873-486d-4dfb-a967-c48f61f237f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399028(v=OCS.15)
ms:contentKeyID: 48185664
ms.date: 12/09/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 878691cd7b39d893b416a128f937d2aad1e561b1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974221"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-enhanced-presence-privacy-mode-in-lync-server-2013"></a><span data-ttu-id="3df91-102">在 Lync Server 2013 中設定增強的目前狀態隱私權模式</span><span class="sxs-lookup"><span data-stu-id="3df91-102">Configuring enhanced presence privacy mode in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3df91-103">_**主題上次修改日期：** 2014-12-08_</span><span class="sxs-lookup"><span data-stu-id="3df91-103">_**Topic Last Modified:** 2014-12-08_</span></span>

<span data-ttu-id="3df91-104">使用者可以使用增強的目前狀態隱私權模式，限制其目前狀態資訊，使其只對 Lync 2013 連絡人清單中所列的連絡人可見。</span><span class="sxs-lookup"><span data-stu-id="3df91-104">With enhanced presence privacy mode, users can restrict their presence information so that it is visible only to the contacts listed in their Lync 2013 Contacts list.</span></span> <span data-ttu-id="3df91-105">**新的-CsPrivacyConfiguration** 和**CsPrivacyConfiguration** Cmdlet 都有一個 EnablePrivacyMode 參數控制此選項。</span><span class="sxs-lookup"><span data-stu-id="3df91-105">The **New-CsPrivacyConfiguration** and **Set-CsPrivacyConfiguration** cmdlets have an EnablePrivacyMode parameter controls this option.</span></span> <span data-ttu-id="3df91-106">當 EnablePrivacyMode 設定為 True 時，會在 Lync 2013 狀態選項中，將目前狀態資訊限制為連絡人的選項。</span><span class="sxs-lookup"><span data-stu-id="3df91-106">When EnablePrivacyMode is set to True, the option to restrict presence information to contacts becomes available in the Lync 2013 Status options.</span></span> <span data-ttu-id="3df91-107">當 EnablePrivacyMode 設定為 False 時，使用者可以選擇 [永遠允許所有人查看其目前狀態資訊]，或遵循系統管理員對隱私權模式所做的任何後續變更。</span><span class="sxs-lookup"><span data-stu-id="3df91-107">When EnablePrivacyMode is set to False, users can choose either to always allow everyone to see their presence information or to adhere to any future changes the administrator makes to the privacy mode.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3df91-108">早期版本（Microsoft Office Communicator 2007 R2 或 Microsoft Office Communicator 2007）不會遵守 lync 2013 和 Lync 2010 隱私權設定。</span><span class="sxs-lookup"><span data-stu-id="3df91-108">Lync 2013 and Lync 2010 privacy settings are not honored by previous versions (Microsoft Office Communicator 2007 R2 or Microsoft Office Communicator 2007).</span></span> <span data-ttu-id="3df91-109">如果允許舊版 Office Communicator 登入，Lync 2013 使用者的狀態、連絡人資訊或圖片可能會被未經授權即可查看的人員所查看。</span><span class="sxs-lookup"><span data-stu-id="3df91-109">If previous versions of Office Communicator are allowed to sign in, a Lync 2013 user’s status, contact information, or picture could be viewed by someone who has not been authorized to view it.</span></span> <span data-ttu-id="3df91-110">此外，如果 Lync 2013 使用者的隱私權設定稍後以舊版 Communicator 登入，就會重設。</span><span class="sxs-lookup"><span data-stu-id="3df91-110">Additionally, a Lync 2013 user’s privacy settings are reset if he or she later signs in with previous version of Communicator.</span></span><BR><span data-ttu-id="3df91-111">基於這些原因，在遷移案例中，在您啟用 [增強的目前狀態隱私權模式] 之前：</span><span class="sxs-lookup"><span data-stu-id="3df91-111">For these reasons, in a migration scenario, before you enable enhanced presence privacy mode:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="3df91-112">確定每位使用者都安裝了 Lync 2013。</span><span class="sxs-lookup"><span data-stu-id="3df91-112">Ensure that every user has Lync 2013 installed.</span></span></P>
> <LI>
> <P><span data-ttu-id="3df91-113">定義用戶端版本原則規則，以防止舊版 Communicator 登入。</span><span class="sxs-lookup"><span data-stu-id="3df91-113">Define a client version policy rule to prevent previous versions of Communicator from signing in.</span></span></P></LI></UL>



</div>

<div>

## <a name="to-enable-enhanced-presence-privacy-mode"></a><span data-ttu-id="3df91-114">啟用增強的目前狀態隱私權模式</span><span class="sxs-lookup"><span data-stu-id="3df91-114">To enable enhanced presence privacy mode</span></span>

1.  <span data-ttu-id="3df91-115">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="3df91-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="3df91-116">執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="3df91-116">Run the following command:</span></span>
    
        Get-CsPrivacyConfiguration | Set-CsPrivacyConfiguration -EnablePrivacyMode $True
    
    <span data-ttu-id="3df91-117">這個命令會針對組織中目前使用的所有隱私權設定啟用 [隱私權模式]。</span><span class="sxs-lookup"><span data-stu-id="3df91-117">This command enables privacy mode for all the privacy configuration settings currently in use in the organization.</span></span> <span data-ttu-id="3df91-118">如需有關 Lync Server 增強的目前狀態隱私權模式原則配置如何管理 Lync 2013 用戶端連絡人目前狀態的詳細資訊，請參閱 Microsoft 知識庫文章[啟用 Lync Server 增強的目前狀態隱私權模式將某些 Lync 連絡人的目前狀態更新為「無法使用](http://support.microsoft.com/kb/3020057)」。</span><span class="sxs-lookup"><span data-stu-id="3df91-118">For more information about how the Lync Server enhanced presence privacy mode policy configurations manages contact presence for the Lync 2013 client, see the Microsoft KB article [Enabling Lync Server enhanced presence privacy mode updates the presence status of some Lync contacts to "unavailable"](http://support.microsoft.com/kb/3020057).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3df91-119">請參閱</span><span class="sxs-lookup"><span data-stu-id="3df91-119">See Also</span></span>


[<span data-ttu-id="3df91-120">CsPrivacyConfiguration</span><span class="sxs-lookup"><span data-stu-id="3df91-120">Get-CsPrivacyConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsPrivacyConfiguration)  
[<span data-ttu-id="3df91-121">新-CsPrivacyConfiguration</span><span class="sxs-lookup"><span data-stu-id="3df91-121">New-CsPrivacyConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsPrivacyConfiguration)  
[<span data-ttu-id="3df91-122">Set-CsPrivacyConfiguration</span><span class="sxs-lookup"><span data-stu-id="3df91-122">Set-CsPrivacyConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

