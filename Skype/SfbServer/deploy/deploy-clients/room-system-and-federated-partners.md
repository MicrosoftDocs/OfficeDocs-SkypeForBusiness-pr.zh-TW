---
title: Skype 房間系統和商務用 Skype 聯盟合作夥伴
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1cc20323-ecba-4e87-a861-e54193e64cf0
description: 請閱讀本主題，瞭解如何針對商務用 Skype 同盟合作夥伴設定 Skype 會議室系統。
ms.openlocfilehash: d5ee83857aa439791e2a31ef201e0f365dbb8408
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768716"
---
# <a name="skype-room-system-and-skype-for-business-federated-partners"></a><span data-ttu-id="aaca7-103">Skype 房間系統和商務用 Skype 聯盟合作夥伴</span><span class="sxs-lookup"><span data-stu-id="aaca7-103">Skype Room System and Skype for Business federated partners</span></span>
 
<span data-ttu-id="aaca7-104">請閱讀本主題，瞭解如何針對商務用 Skype 同盟合作夥伴設定 Skype 會議室系統。</span><span class="sxs-lookup"><span data-stu-id="aaca7-104">Read this topic to learn how to set up Skype Room System for Skype for Business federated partners.</span></span>
  
## <a name="skype-room-system-and-skype-for-business-federated-partners"></a><span data-ttu-id="aaca7-105">Skype 房間系統和商務用 Skype 聯盟合作夥伴</span><span class="sxs-lookup"><span data-stu-id="aaca7-105">Skype Room System and Skype for Business federated partners</span></span>

<span data-ttu-id="aaca7-106">Skype 會議室系統依賴行事曆會議邀請中的 [加入商務用 Skype 會議] 連結。</span><span class="sxs-lookup"><span data-stu-id="aaca7-106">Skype Room System relies on the Join Skype for Business Meeting link in the calendar meeting request.</span></span> <span data-ttu-id="aaca7-107">加入連結通常是在會議邀請內文中找到。</span><span class="sxs-lookup"><span data-stu-id="aaca7-107">The join link is usually found in the body of a meeting request.</span></span> <span data-ttu-id="aaca7-108">不過，Skype 房間系統依賴此連結，就會出現在郵件的 MAPI 屬性中。</span><span class="sxs-lookup"><span data-stu-id="aaca7-108">However, Skype Room System depends on this link to be present in the MAPI properties of the message.</span></span> <span data-ttu-id="aaca7-109">當此會議邀請傳送至遠端組織（商務用 Skype 同盟合作夥伴）時，預設情況下，遠端組織的 Skype 會議室系統不會顯示行事曆上的 [會議加入] 連結。</span><span class="sxs-lookup"><span data-stu-id="aaca7-109">When this meeting request is sent to remote organizations (Skype for Business federated partners), by default the remote organization's Skype Room System will not show the meeting join link on the calendar.</span></span> <span data-ttu-id="aaca7-110">事實上，遠端組織中的任何 Outlook 使用者都無法以滑鼠右鍵按一下行事曆專案或從會議提醒中加入商務用 Skype 會議。</span><span class="sxs-lookup"><span data-stu-id="aaca7-110">In fact, any Outlook users in the remote organization will be unable to join the Skype for Business meeting with a right click of the calendar item or from within the meeting reminder.</span></span> <span data-ttu-id="aaca7-111">他們必須開啟會議邀請，然後按一下郵件本文中的 [加入商務用 Skype 會議]。</span><span class="sxs-lookup"><span data-stu-id="aaca7-111">They must open meeting invite and click Join Skype for Business Meeting in the body of the message.</span></span> 
  
<span data-ttu-id="aaca7-112">這個限制的原因是 Outlook 和 Microsoft Exchange 不使用特殊的方法封裝資訊，以便在網際網路上傳送郵件。</span><span class="sxs-lookup"><span data-stu-id="aaca7-112">The reason for this limitation is that Outlook and Microsoft Exchange do not use a special method to package information for sending messages across the Internet.</span></span> <span data-ttu-id="aaca7-113">此方法稱為 [傳輸中性封裝格式（TNEF）]，預設為從 Exchange 組織外部傳送的郵件停用。</span><span class="sxs-lookup"><span data-stu-id="aaca7-113">This method, referred to as Transport Neutral Encapsulation Format (TNEF), is disabled by default for messages sent externally from an Exchange organization.</span></span> <span data-ttu-id="aaca7-114">若要在遠端 Skype 聊天室系統上顯示會議加入連結，傳送組織必須使用下列命令來啟用 TNEF：</span><span class="sxs-lookup"><span data-stu-id="aaca7-114">For a meeting join link to appear on a remote Skype Room System, the sending organization must enable TNEF by using the following command:</span></span>
  
```powershell
New-RemoteDomain -DomainName Contoso.com -Name Contoso
Set-RemoteDomain -Identity Contoso -TNEFEnabled $true
```

<span data-ttu-id="aaca7-115">在遠端組織啟用 TNEF 之後，透過網際網路傳送的任何郵件都會以 TNEF 格式的附件傳送給組織。</span><span class="sxs-lookup"><span data-stu-id="aaca7-115">After TNEF is enabled for the remote organization, any message sent over the Internet to the organization is sent as an attachment in TNEF format.</span></span> <span data-ttu-id="aaca7-116">在已啟用 TNEF 的情況下，當商務用 skype 會議邀請傳送到商務用 Skype 同盟合作夥伴時，Skype 室系統將能夠轉譯商務用 skype 會議，而遠端使用者將能夠加入商務用 Skype 會議。</span><span class="sxs-lookup"><span data-stu-id="aaca7-116">With TNEF enabled, when a Skype for Business meeting request is sent to the Skype for Business federated partner, Skype Room System will be able to render the Join Skype for Business Meeting and remote users will be able to join Skype for Business meetings.</span></span> 
