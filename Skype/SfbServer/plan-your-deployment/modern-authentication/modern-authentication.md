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
description: 規劃商務用 Skype Server 的驗證及授權主題，包括與其他產品的整合
ms.openlocfilehash: f732e4afa6b82554c4248a244276e5e5b60c71cc
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815841"
---
# <a name="discussing-authentication-and-authorization-in-skype-for-business"></a><span data-ttu-id="6c8a0-103">在商務用 Skype 中討論驗證與授權</span><span class="sxs-lookup"><span data-stu-id="6c8a0-103">Discussing Authentication and Authorization in Skype for Business</span></span>

<span data-ttu-id="6c8a0-104">驗證與授權是相關概念，但對您執行不同的工作（雖然這兩者都是必要的）。</span><span class="sxs-lookup"><span data-stu-id="6c8a0-104">Authentication and authorization are related concepts, but do different work for you (though both are necessary).</span></span> <span data-ttu-id="6c8a0-105">以簡單的詞彙為 authenciation （AuthN），只會根據機密使用者知道或擁有的密碼，也可以是密碼、代碼、指紋、憑證、聲明關於使用者的宣告組合，或是共同使用這些專案的組合。</span><span class="sxs-lookup"><span data-stu-id="6c8a0-105">Put in simple terms, authenciation (AuthN) depends on secrets only a valid user knows or has, and that can be a password, code, fingerprint, certificate, a combination of claims about the user that are true, or a combination of these things used together.</span></span> <span data-ttu-id="6c8a0-106">AuthN 是一個處理常式，可以證明您是自己所說的人。</span><span class="sxs-lookup"><span data-stu-id="6c8a0-106">AuthN is a process out to prove you are who you say you are.</span></span>

<span data-ttu-id="6c8a0-107">授權（AuthZ）與您驗證您的身份之後，就會與您有權存取的專案相關。</span><span class="sxs-lookup"><span data-stu-id="6c8a0-107">Authorization (AuthZ) is concerned with what you have access to after you've proven who you are.</span></span> <span data-ttu-id="6c8a0-108">它會判斷您已允許查看、編輯及以其他方式存取的專案。</span><span class="sxs-lookup"><span data-stu-id="6c8a0-108">It determines what you've been allowed to see, edit, and otherwise access.</span></span> <span data-ttu-id="6c8a0-109">例如，您可能具備 SharePoint Online 的強大網站集合管理員存取權，但如果您切換到另一個線上工作負載（例如商務用 Skype Online），您可能有權對使用者問題進行疑難排解，而不會變更其設定伺服器或伺服器。</span><span class="sxs-lookup"><span data-stu-id="6c8a0-109">For example, you may have powerful Site Collection Administrator access to SharePoint Online, but if you switch to another online workload, like Skype for Business Online, you may have the privileges to troubleshoot user issues, not change the configuration of the server or servers.</span></span> <span data-ttu-id="6c8a0-110">在第三個工作負荷（例如 Exchange Online）中，您可能只會擁有一般使用者的存取權。</span><span class="sxs-lookup"><span data-stu-id="6c8a0-110">In a third workload, such as Exchange Online, you might only have the average user's access.</span></span> <span data-ttu-id="6c8a0-111">AuthZ 會檢查您對服務/worloads、應用程式、檔案及其他資料所擁有的存取權。</span><span class="sxs-lookup"><span data-stu-id="6c8a0-111">AuthZ checks what and how much access you have to services/worloads, applications, files, and other data.</span></span>

<span data-ttu-id="6c8a0-112">我們的範例涉及 SharePoint 和 Exchange online 等線上屬性，但 AuthN 和 AuthZ 的處理常式在內部部署及混合式部署中都是相同的。</span><span class="sxs-lookup"><span data-stu-id="6c8a0-112">Our examples involve online properties like SharePoint and Exchange online, but the processes of AuthN and AuthZ work on-premises and in a hybrid premises the same way.</span></span> <span data-ttu-id="6c8a0-113">最後，諸如 AAD Connect 和 ADFS 之類的工具，只要將內部部署帳戶和密碼同步處理到雲端的廣告（在 Office 365 或 Azure 中則是 Azure AD），或是在授權流程中 intruding，就能讓使用者通常不會收到其認證的提示，比如說，在雲端中切換工作負載時，建立單一登入案例。</span><span class="sxs-lookup"><span data-stu-id="6c8a0-113">Ultimately, tools like AAD Connect and ADFS become involved in the AuthN and AuthZ story by either synchronizing on-premises accounts and passwords into the Cloud's AD (which is Azure AD in the case of either Office 365 or Azure), or intruding in the flow of AuthZ so that a user isn't frequently prompted for their credentials, say when switching between workloads in the Cloud, creating Single Sign-On scenarios.</span></span> <span data-ttu-id="6c8a0-114">但它們本身不是由責任 AuthN 或 AuthZ 所組成，只是其中一個機制。</span><span class="sxs-lookup"><span data-stu-id="6c8a0-114">But they aren't, in themselves, responsible AuthN or AuthZ, just part of the mechanics.</span></span>

<span data-ttu-id="6c8a0-115">今天，許多技術會將這些程式（AuthN 和 AuthZ）視為單一機制，而且您會聽到許多對驗證程式的參考，也就是在其中加入授權。</span><span class="sxs-lookup"><span data-stu-id="6c8a0-115">Today, many technologies consider these processes (AuthN and AuthZ) to be one mechanism, and you'll hear many references to authentication process that also include authorization in them.</span></span> <span data-ttu-id="6c8a0-116">請務必記住，使用者存取中的第一個步驟是 AuthN，證明您是誰所說的人員，而且該 AuthZ 人員會使用使用者決定有權存取權的人員（如您在開啟授權或 OAuth 中所看到的內容）。</span><span class="sxs-lookup"><span data-stu-id="6c8a0-116">It's important to remember that the first step in user access is AuthN, proving you are who you say you are, and that AuthZ uses the knowledge of who the user is to determine what he or she has access to (as you'll see with Open Authorization or OAuth).</span></span>

  
## <a name="authentication-and-authorization-planning-topics"></a><span data-ttu-id="6c8a0-117">驗證與授權規劃主題</span><span class="sxs-lookup"><span data-stu-id="6c8a0-117">Authentication and Authorization Planning Topics</span></span>

[<span data-ttu-id="6c8a0-118">如何在商務用 Skype 中使用新式驗證（ADAL）</span><span class="sxs-lookup"><span data-stu-id="6c8a0-118">How to use Modern Authentication (ADAL) with Skype for Business</span></span>](plan-adal.md)

[<span data-ttu-id="6c8a0-119">現代驗證支援的商務用 Skype 拓撲</span><span class="sxs-lookup"><span data-stu-id="6c8a0-119">Skype for Business topologies supported with Modern Authentication</span></span>](topologies-supported.md)

[<span data-ttu-id="6c8a0-120">規劃在內部和外部將舊版驗證方法關閉至您的網路。</span><span class="sxs-lookup"><span data-stu-id="6c8a0-120">Planning to turn off Legacy authentication methods internally and externally to your network.</span></span>](turn-on-modern-auth.md)

