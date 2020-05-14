---
title: 在商務用 Skype 中規劃新式驗證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 25e68396-96dc-4e4b-8a65-d30ea80d1bc9
description: 規劃商務用 Skype Server 的驗證和授權主題，包括與其他產品的整合
ms.openlocfilehash: 3b673a9f88895ac57277ef51b51fe0a4a27c64a2
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221577"
---
# <a name="discussing-authentication-and-authorization-in-skype-for-business"></a><span data-ttu-id="4ab53-103">在商務用 Skype 中討論驗證和授權</span><span class="sxs-lookup"><span data-stu-id="4ab53-103">Discussing Authentication and Authorization in Skype for Business</span></span>

<span data-ttu-id="4ab53-104">驗證和授權是相關的概念，但為您執行不同的工作（雖然兩者都是必要的）。</span><span class="sxs-lookup"><span data-stu-id="4ab53-104">Authentication and authorization are related concepts, but do different work for you (though both are necessary).</span></span> <span data-ttu-id="4ab53-105">放入簡易的字詞中，authenciation （AuthN）只取決於機密有效的使用者，且可以是密碼、程式碼、指紋、憑證、使用者對 true 的宣告組合，或是這些專案一起使用的組合。</span><span class="sxs-lookup"><span data-stu-id="4ab53-105">Put in simple terms, authenciation (AuthN) depends on secrets only a valid user knows or has, and that can be a password, code, fingerprint, certificate, a combination of claims about the user that are true, or a combination of these things used together.</span></span> <span data-ttu-id="4ab53-106">AuthN 是一種可證明您是否為您所說的使用者的處理常式。</span><span class="sxs-lookup"><span data-stu-id="4ab53-106">AuthN is a process out to prove you are who you say you are.</span></span>

<span data-ttu-id="4ab53-107">授權（AuthZ）與您驗證您的人選後，與您可以存取的內容相關。</span><span class="sxs-lookup"><span data-stu-id="4ab53-107">Authorization (AuthZ) is concerned with what you have access to after you've proven who you are.</span></span> <span data-ttu-id="4ab53-108">它會決定您已允許查看、編輯或以其他方式存取的專案。</span><span class="sxs-lookup"><span data-stu-id="4ab53-108">It determines what you've been allowed to see, edit, and otherwise access.</span></span> <span data-ttu-id="4ab53-109">例如，您可能具有 SharePoint 線上的功能強大的網站集合管理員存取權，但是如果您切換到另一個線上工作負載（如商務用 Skype Online），您可能會具備疑難排解使用者問題的許可權，而不會變更伺服器或伺服器的設定。</span><span class="sxs-lookup"><span data-stu-id="4ab53-109">For example, you may have powerful Site Collection Administrator access to SharePoint Online, but if you switch to another online workload, like Skype for Business Online, you may have the privileges to troubleshoot user issues, not change the configuration of the server or servers.</span></span> <span data-ttu-id="4ab53-110">在第三個工作負載中（例如 Exchange Online），您可能只會具備平均使用者的存取權。</span><span class="sxs-lookup"><span data-stu-id="4ab53-110">In a third workload, such as Exchange Online, you might only have the average user's access.</span></span> <span data-ttu-id="4ab53-111">AuthZ 會檢查您對服務/worloads、應用程式、檔案及其他資料的存取權。</span><span class="sxs-lookup"><span data-stu-id="4ab53-111">AuthZ checks what and how much access you have to services/worloads, applications, files, and other data.</span></span>

<span data-ttu-id="4ab53-112">我們的範例包括 SharePoint 和 Exchange online 等線上屬性，但 AuthN 和 AuthZ 的處理常式會以相同的方式，在內部部署和混合式部署中運作。</span><span class="sxs-lookup"><span data-stu-id="4ab53-112">Our examples involve online properties like SharePoint and Exchange online, but the processes of AuthN and AuthZ work on-premises and in a hybrid premises the same way.</span></span> <span data-ttu-id="4ab53-113">最後，當您將內部部署帳戶和密碼同步處理至雲端的 AD （即 Azure AD），或在授權流程中 intruding，讓使用者不會經常提示他們的認證，例如，在雲端中切換工作負載時，建立單一 Sign-On 案例，就像 AAD Connect 和 ADFS 之類的工具，就會包含在 AuthN 和 AuthZ 中。</span><span class="sxs-lookup"><span data-stu-id="4ab53-113">Ultimately, tools like AAD Connect and ADFS become involved in the AuthN and AuthZ story by either synchronizing on-premises accounts and passwords into the Cloud's AD (which is Azure AD), or intruding in the flow of AuthZ so that a user isn't frequently prompted for their credentials, say when switching between workloads in the Cloud, creating Single Sign-On scenarios.</span></span> <span data-ttu-id="4ab53-114">不過，他們本身不負責 AuthN 或 AuthZ，只是部分機制。</span><span class="sxs-lookup"><span data-stu-id="4ab53-114">But they aren't, in themselves, responsible AuthN or AuthZ, just part of the mechanics.</span></span>

<span data-ttu-id="4ab53-115">目前，許多技術會將這些程式（AuthN 和 AuthZ）視為一種機制，您會聽到許多對驗證程式的參考，也就是在這些程式中包含授權。</span><span class="sxs-lookup"><span data-stu-id="4ab53-115">Today, many technologies consider these processes (AuthN and AuthZ) to be one mechanism, and you'll hear many references to authentication process that also include authorization in them.</span></span> <span data-ttu-id="4ab53-116">請務必記住，使用者存取中的第一步是 AuthN，證明您是由您所說的，而該 AuthZ 人員會使用他們的知識來決定誰可以存取誰（如您將會看到開啟的授權或 OAuth）。</span><span class="sxs-lookup"><span data-stu-id="4ab53-116">It's important to remember that the first step in user access is AuthN, proving you are who you say you are, and that AuthZ uses the knowledge of who the user is to determine what he or she has access to (as you'll see with Open Authorization or OAuth).</span></span>

  
## <a name="authentication-and-authorization-planning-topics"></a><span data-ttu-id="4ab53-117">驗證和授權規劃主題</span><span class="sxs-lookup"><span data-stu-id="4ab53-117">Authentication and Authorization Planning Topics</span></span>

[<span data-ttu-id="4ab53-118">如何使用現代驗證（ADAL）搭配商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="4ab53-118">How to use Modern Authentication (ADAL) with Skype for Business</span></span>](plan-adal.md)

[<span data-ttu-id="4ab53-119">新式驗證支援的商務用 Skype 拓撲</span><span class="sxs-lookup"><span data-stu-id="4ab53-119">Skype for Business topologies supported with Modern Authentication</span></span>](topologies-supported.md)

[<span data-ttu-id="4ab53-120">規劃在內部和外部關閉舊版驗證方法。</span><span class="sxs-lookup"><span data-stu-id="4ab53-120">Planning to turn off Legacy authentication methods internally and externally to your network.</span></span>](turn-on-modern-auth.md)

