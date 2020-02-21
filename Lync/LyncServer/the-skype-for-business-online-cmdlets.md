---
title: Skype 商務 Online cmdlet
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: The Skype for Business Online cmdlets
ms:assetid: 71f38305-fd8b-4013-83e1-cb742e3174c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362817(v=OCS.15)
ms:contentKeyID: 56558831
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02365bfeeed60a22ea467091ebb0f2c92b0fa3c2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189186"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="the-skype-for-business-online-cmdlets"></a><span data-ttu-id="e7b99-102">Skype 商務 Online cmdlet</span><span class="sxs-lookup"><span data-stu-id="e7b99-102">The Skype for Business Online cmdlets</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e7b99-103">_**上次修改主題：** 2013年-07-05_</span><span class="sxs-lookup"><span data-stu-id="e7b99-103">_**Topic Last Modified:** 2013-07-05_</span></span>

<span data-ttu-id="e7b99-104">當您連接至 Skype for Business Online 使用 Windows PowerShell 時，一群 Skype for Business Online 指令程式會複製，在記憶體中，到您的電腦。</span><span class="sxs-lookup"><span data-stu-id="e7b99-104">When you connect to Skype for Business Online by using Windows PowerShell, a collection of Skype for Business Online cmdlets is copied, in memory, to your computer.</span></span> <span data-ttu-id="e7b99-105">這些指令程式，除了您已經在您的本機電腦 （包括當您安裝 Windows PowerShell 安裝的核心 cmdlet） 的任何其他 cmdlet 就適用於管理您 Skype for Business Online 部署與您商務用 Skype商務線上的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="e7b99-105">These cmdlets, in addition to any other cmdlets you already have on your local computer (including the core cmdlets that are installed when you install Windows PowerShell), are then available for managing your Skype for Business Online deployment and your Skype for Business Online user accounts.</span></span> <span data-ttu-id="e7b99-106">Skype 商務 Online 指令程式中導入下列主題：</span><span class="sxs-lookup"><span data-stu-id="e7b99-106">The Skype for Business Online cmdlets are introduced in the following topics:</span></span>

  - [<span data-ttu-id="e7b99-107">管理商務用 Skype 商務 Online 租用戶</span><span class="sxs-lookup"><span data-stu-id="e7b99-107">Managing Skype for Business Online tenants</span></span>](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/manage-skype-for-business-online-organizations)

  - [<span data-ttu-id="e7b99-108">管理使用者與 Skype for Business Online 中的使用者帳戶內容</span><span class="sxs-lookup"><span data-stu-id="e7b99-108">Managing users and user account properties in Skype for Business Online</span></span>](https://docs.microsoft.com/skypeforbusiness/manage/user-accounts/user-accounts)

  - [<span data-ttu-id="e7b99-109">Skype 商務 Online 中的管理原則</span><span class="sxs-lookup"><span data-stu-id="e7b99-109">Managing policies in Skype for Business Online</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-policies-with-office-365-powershell)

  - [<span data-ttu-id="e7b99-110">商務用 Skype 管理 Skype 商務用戶端</span><span class="sxs-lookup"><span data-stu-id="e7b99-110">Managing the Skype for Business client from Skype for Business Online</span></span>](https://docs.microsoft.com/skypeforbusiness/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365)

  - [<span data-ttu-id="e7b99-111">管理 Exchange 整合通訊與 skype for Business Online 託管的語音信箱</span><span class="sxs-lookup"><span data-stu-id="e7b99-111">Managing Exchange Unified Messaging and hosted voice mail in Skype for Business Online</span></span>](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/manage-exchange-unified-messaging-and-hosted-voicemail)

  - [<span data-ttu-id="e7b99-112">管理通訊 skype for Business Online 與外部使用者和組織</span><span class="sxs-lookup"><span data-stu-id="e7b99-112">Managing communications in Skype for Business Online with outside users and organizations</span></span>](https://docs.microsoft.com/skypeforbusiness/set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users)

  - [<span data-ttu-id="e7b99-113">管理商務用 Skype 商務線上會議及會議</span><span class="sxs-lookup"><span data-stu-id="e7b99-113">Managing Skype for Business Online meetings and conferences</span></span>](https://docs.microsoft.com/skypeforbusiness/manage/conferencing/conferencing-policies)

  - [<span data-ttu-id="e7b99-114">管理行動電話和商務用 Skype 中的行動裝置</span><span class="sxs-lookup"><span data-stu-id="e7b99-114">Managing cell phones and mobile devices in Skype for Business Online</span></span>](https://docs.microsoft.com/skypeforbusiness/set-up-policies-in-your-organization/set-up-mobile-policies-for-your-organization)

<div>

## <a name="see-also"></a><span data-ttu-id="e7b99-115">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e7b99-115">See Also</span></span>


[<span data-ttu-id="e7b99-116">快速參考： 使用 Windows PowerShell 來執行一般 Skype for Business Online 的管理工作</span><span class="sxs-lookup"><span data-stu-id="e7b99-116">Quick reference: Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

