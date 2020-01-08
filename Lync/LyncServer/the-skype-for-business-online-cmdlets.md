---
title: Lync Online Cmdlet
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: The Skype for Business Online cmdlets
ms:assetid: 71f38305-fd8b-4013-83e1-cb742e3174c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362817(v=OCS.15)
ms:contentKeyID: 56558831
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1994843eb2059045525c61c5821051add2d30b47
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978155"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="the-skype-for-business-online-cmdlets"></a><span data-ttu-id="704eb-102">Lync Online Cmdlet</span><span class="sxs-lookup"><span data-stu-id="704eb-102">The Skype for Business Online cmdlets</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="704eb-103">_**主題上次修改日期：** 2013-07-05_</span><span class="sxs-lookup"><span data-stu-id="704eb-103">_**Topic Last Modified:** 2013-07-05_</span></span>

<span data-ttu-id="704eb-104">當您使用 Windows PowerShell 連線到商務用 Skype Online 時，系統會將商務用 Skype Online Cmdlet 集合複製到您的電腦。</span><span class="sxs-lookup"><span data-stu-id="704eb-104">When you connect to Skype for Business Online by using Windows PowerShell, a collection of Skype for Business Online cmdlets is copied, in memory, to your computer.</span></span> <span data-ttu-id="704eb-105">這些 Cmdlet 除了您在本機電腦上已有的任何其他 Cmdlet （包括安裝 Windows PowerShell 時安裝的核心 Cmdlet），都可供您用來管理商務用 Skype Online 部署和 Skype商務用 Online 使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="704eb-105">These cmdlets, in addition to any other cmdlets you already have on your local computer (including the core cmdlets that are installed when you install Windows PowerShell), are then available for managing your Skype for Business Online deployment and your Skype for Business Online user accounts.</span></span> <span data-ttu-id="704eb-106">商務用 Skype Online Cmdlet 會在下列主題仲介紹：</span><span class="sxs-lookup"><span data-stu-id="704eb-106">The Skype for Business Online cmdlets are introduced in the following topics:</span></span>

  - [<span data-ttu-id="704eb-107">管理 Lync Online 租用戶</span><span class="sxs-lookup"><span data-stu-id="704eb-107">Managing Skype for Business Online tenants</span></span>](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/manage-skype-for-business-online-organizations)

  - [<span data-ttu-id="704eb-108">在商務用 Skype Online 中管理使用者和使用者帳戶屬性</span><span class="sxs-lookup"><span data-stu-id="704eb-108">Managing users and user account properties in Skype for Business Online</span></span>](https://docs.microsoft.com/skypeforbusiness/manage/user-accounts/user-accounts)

  - [<span data-ttu-id="704eb-109">管理商務用 Skype Online 中的原則</span><span class="sxs-lookup"><span data-stu-id="704eb-109">Managing policies in Skype for Business Online</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-policies-with-office-365-powershell)

  - [<span data-ttu-id="704eb-110">從商務用 Skype Online 管理商務用 Skype 用戶端</span><span class="sxs-lookup"><span data-stu-id="704eb-110">Managing the Skype for Business client from Skype for Business Online</span></span>](https://docs.microsoft.com/skypeforbusiness/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365)

  - [<span data-ttu-id="704eb-111">在商務用 Skype Online 中管理 Exchange 整合訊息及託管語音信箱</span><span class="sxs-lookup"><span data-stu-id="704eb-111">Managing Exchange Unified Messaging and hosted voice mail in Skype for Business Online</span></span>](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/manage-exchange-unified-messaging-and-hosted-voicemail)

  - [<span data-ttu-id="704eb-112">管理與外部使用者和組織在商務用 Skype Online 中的通訊</span><span class="sxs-lookup"><span data-stu-id="704eb-112">Managing communications in Skype for Business Online with outside users and organizations</span></span>](https://docs.microsoft.com/skypeforbusiness/set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users)

  - [<span data-ttu-id="704eb-113">管理 Lync 線上會議與會議</span><span class="sxs-lookup"><span data-stu-id="704eb-113">Managing Skype for Business Online meetings and conferences</span></span>](https://docs.microsoft.com/skypeforbusiness/manage/conferencing/conferencing-policies)

  - [<span data-ttu-id="704eb-114">管理商務用 Skype Online 中的手機與行動裝置</span><span class="sxs-lookup"><span data-stu-id="704eb-114">Managing cell phones and mobile devices in Skype for Business Online</span></span>](https://docs.microsoft.com/skypeforbusiness/set-up-policies-in-your-organization/set-up-mobile-policies-for-your-organization)

<div>

## <a name="see-also"></a><span data-ttu-id="704eb-115">請參閱</span><span class="sxs-lookup"><span data-stu-id="704eb-115">See Also</span></span>


[<span data-ttu-id="704eb-116">快速參考：使用 Windows PowerShell 執行 Lync Online 的一般管理工作</span><span class="sxs-lookup"><span data-stu-id="704eb-116">Quick reference: Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

