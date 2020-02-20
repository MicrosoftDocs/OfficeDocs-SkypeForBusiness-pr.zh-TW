---
title: Lync Server 2013： 設定增強的目前狀態隱私權模式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring enhanced presence privacy mode
ms:assetid: e7a6b873-486d-4dfb-a967-c48f61f237f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399028(v=OCS.15)
ms:contentKeyID: 48185664
ms.date: 12/09/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 91326778777e6ddd1db2f8938cfb78e96ed8c7f5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151565"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-enhanced-presence-privacy-mode-in-lync-server-2013"></a><span data-ttu-id="2fe34-102">在 Lync Server 2013 中設定增強的目前狀態隱私權模式</span><span class="sxs-lookup"><span data-stu-id="2fe34-102">Configuring enhanced presence privacy mode in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2fe34-103">_**上次修改主題：** 2014年-12-08_</span><span class="sxs-lookup"><span data-stu-id="2fe34-103">_**Topic Last Modified:** 2014-12-08_</span></span>

<span data-ttu-id="2fe34-104">使用增強顯示狀態隱私權模式時，使用者可以限制其目前狀態資訊，使其只能看見其 Lync 2013 連絡人清單中所列的連絡人。</span><span class="sxs-lookup"><span data-stu-id="2fe34-104">With enhanced presence privacy mode, users can restrict their presence information so that it is visible only to the contacts listed in their Lync 2013 Contacts list.</span></span> <span data-ttu-id="2fe34-105">**新增 CsPrivacyConfiguration** 和**Set-csprivacyconfiguration** cmdlet 有 EnablePrivacyMode 參數會控制此選項。</span><span class="sxs-lookup"><span data-stu-id="2fe34-105">The **New-CsPrivacyConfiguration** and **Set-CsPrivacyConfiguration** cmdlets have an EnablePrivacyMode parameter controls this option.</span></span> <span data-ttu-id="2fe34-106">當 EnablePrivacyMode 設為 True 時，限制為連絡人的目前狀態資訊的選項會變成中的 Lync 2013 狀態選項可用。</span><span class="sxs-lookup"><span data-stu-id="2fe34-106">When EnablePrivacyMode is set to True, the option to restrict presence information to contacts becomes available in the Lync 2013 Status options.</span></span> <span data-ttu-id="2fe34-107">EnablePrivacyMode 時設為 False，使用者可以選擇 [永遠允許所有人都看到其目前狀態資訊，或為遵守未來的任何變更系統管理員對 [隱私權模式。</span><span class="sxs-lookup"><span data-stu-id="2fe34-107">When EnablePrivacyMode is set to False, users can choose either to always allow everyone to see their presence information or to adhere to any future changes the administrator makes to the privacy mode.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2fe34-108">Lync 2013 和 Lync 2010 的隱私權設定不會生效前一個版本 （Microsoft Office Communicator 2007 R2 或 Microsoft Office Communicator 2007）。</span><span class="sxs-lookup"><span data-stu-id="2fe34-108">Lync 2013 and Lync 2010 privacy settings are not honored by previous versions (Microsoft Office Communicator 2007 R2 or Microsoft Office Communicator 2007).</span></span> <span data-ttu-id="2fe34-109">如果舊版 Office Communicator 允許登入 Lync 2013 使用者的狀態，請連絡資訊，或由不已經若要檢視其授權的人員可以檢視圖片。</span><span class="sxs-lookup"><span data-stu-id="2fe34-109">If previous versions of Office Communicator are allowed to sign in, a Lync 2013 user’s status, contact information, or picture could be viewed by someone who has not been authorized to view it.</span></span> <span data-ttu-id="2fe34-110">此外，如果他或她稍後與舊版 Communicator 登入時，會重設 Lync 2013 使用者隱私權設定。</span><span class="sxs-lookup"><span data-stu-id="2fe34-110">Additionally, a Lync 2013 user’s privacy settings are reset if he or she later signs in with previous version of Communicator.</span></span><BR><span data-ttu-id="2fe34-111">基於這些理由，在移轉案例中，才能啟用增強型目前狀態隱私權模式：</span><span class="sxs-lookup"><span data-stu-id="2fe34-111">For these reasons, in a migration scenario, before you enable enhanced presence privacy mode:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="2fe34-112">確定每個使用者具有安裝 Lync 2013。</span><span class="sxs-lookup"><span data-stu-id="2fe34-112">Ensure that every user has Lync 2013 installed.</span></span></P>
> <LI>
> <P><span data-ttu-id="2fe34-113">定義以防止舊版 Communicator 登入的用戶端版本原則規則。</span><span class="sxs-lookup"><span data-stu-id="2fe34-113">Define a client version policy rule to prevent previous versions of Communicator from signing in.</span></span></P></LI></UL>



</div>

<div>

## <a name="to-enable-enhanced-presence-privacy-mode"></a><span data-ttu-id="2fe34-114">若要啟用增強型目前狀態隱私權模式</span><span class="sxs-lookup"><span data-stu-id="2fe34-114">To enable enhanced presence privacy mode</span></span>

1.  <span data-ttu-id="2fe34-115">啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="2fe34-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="2fe34-116">執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="2fe34-116">Run the following command:</span></span>
    
        Get-CsPrivacyConfiguration | Set-CsPrivacyConfiguration -EnablePrivacyMode $True
    
    <span data-ttu-id="2fe34-117">此命令可啟用隱私權模式目前組織中的使用中的所有隱私組態設定。</span><span class="sxs-lookup"><span data-stu-id="2fe34-117">This command enables privacy mode for all the privacy configuration settings currently in use in the organization.</span></span> <span data-ttu-id="2fe34-118">如需關於如何在 Lync 伺服器增強型目前狀態隱私權模式原則設定，請管理 Lync 2013 用戶端的連絡人的目前狀態，請參閱 Microsoft 知識庫文章[啟用 Lync Server 增強顯示狀態隱私權模式更新 「 無法使用 」 部分 Lync 連絡人的目前狀態](https://support.microsoft.com/kb/3020057)。</span><span class="sxs-lookup"><span data-stu-id="2fe34-118">For more information about how the Lync Server enhanced presence privacy mode policy configurations manages contact presence for the Lync 2013 client, see the Microsoft KB article [Enabling Lync Server enhanced presence privacy mode updates the presence status of some Lync contacts to "unavailable"](https://support.microsoft.com/kb/3020057).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2fe34-119">另請參閱</span><span class="sxs-lookup"><span data-stu-id="2fe34-119">See Also</span></span>


[<span data-ttu-id="2fe34-120">Get-csprivacyconfiguration</span><span class="sxs-lookup"><span data-stu-id="2fe34-120">Get-CsPrivacyConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsPrivacyConfiguration)  
[<span data-ttu-id="2fe34-121">New-csprivacyconfiguration</span><span class="sxs-lookup"><span data-stu-id="2fe34-121">New-CsPrivacyConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsPrivacyConfiguration)  
[<span data-ttu-id="2fe34-122">Set-csprivacyconfiguration</span><span class="sxs-lookup"><span data-stu-id="2fe34-122">Set-CsPrivacyConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

