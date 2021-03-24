---
title: 使用商務用 Skype) 規劃新式驗證 (ADAL
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 本文說明使用 Active Directory 驗證程式庫 (ADAL) 和 OAuth 2.0) 的新式驗證 (。
ms.openlocfilehash: 1df07491881b90efc16c97e7cd5cec0953cfb346
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096609"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a><span data-ttu-id="35dbc-103">如何搭配商務用 Skype) 使用新式驗證 (ADAL</span><span class="sxs-lookup"><span data-stu-id="35dbc-103">How to use Modern Authentication (ADAL) with Skype for Business</span></span>
 
<span data-ttu-id="35dbc-104">本文介紹新式驗證 (，這是根據 Active Directory 驗證程式庫 (ADAL) 和 OAuth 2.0) ，可在商務用 skype Server 2015 的三月份2016累積更新中找到，或是從商務用 Skype Server 2019 的初始版本取得。</span><span class="sxs-lookup"><span data-stu-id="35dbc-104">This article introduces Modern Authentication (which is based on the Active Directory Authentication Library (ADAL) and OAuth 2.0) that can be found in the March 2016 Cumulative Update for Skype for Business for Skype for Business Server 2015, or from initial release for Skype for Business Server 2019.</span></span>
  
## <a name="what-is-adal"></a><span data-ttu-id="35dbc-105">什麼是 ADAL？</span><span class="sxs-lookup"><span data-stu-id="35dbc-105">What is ADAL?</span></span>

<span data-ttu-id="35dbc-106">ADAL 是「Active Directory 驗證程式庫」的縮寫，以及 OAuth 2.0，是新式驗證的基礎。</span><span class="sxs-lookup"><span data-stu-id="35dbc-106">ADAL is the acronym for the 'Active Directory Authentication Library', and, along with OAuth 2.0, it is an underpinning of Modern Authentication.</span></span> <span data-ttu-id="35dbc-107">此程式碼庫的設計目的是讓您的目錄中的安全資源可供用戶端應用程式使用 (例如商務用 Skype) 透過安全性權杖。</span><span class="sxs-lookup"><span data-stu-id="35dbc-107">This code library is designed to make secured resources in your directory available to client applications (like Skype for Business) via security tokens.</span></span> <span data-ttu-id="35dbc-108">ADAL 可與 OAuth 2.0 搭配使用，以啟用更多驗證和授權案例，例如多重要素驗證 (MFA) 和其他形式的 SAML Auth。</span><span class="sxs-lookup"><span data-stu-id="35dbc-108">ADAL works with OAuth 2.0 to enable more authentication and authorization scenarios, like Multi-factor Authentication (MFA), and more forms of SAML Auth.</span></span>
  
<span data-ttu-id="35dbc-109">可充當用戶端的各種應用程式可利用新式驗證取得安全資源的協助。</span><span class="sxs-lookup"><span data-stu-id="35dbc-109">A variety of apps that act as clients can leverage Modern Authentication for help in getting to secured resources.</span></span> <span data-ttu-id="35dbc-110">在商務用 Skype Server 中，此技術是用於內部部署用戶端和內部部署伺服器，以便為使用者提供適當的資源授權層級。</span><span class="sxs-lookup"><span data-stu-id="35dbc-110">In Skype for Business Server, this technology is used between on-premises clients and on-premises servers in order to give users a proper level of authorization to resources.</span></span>
  
<span data-ttu-id="35dbc-111">新式驗證交談 (以 ADAL 和 OAuth 2.0 為基礎) 具有一些共同元素。</span><span class="sxs-lookup"><span data-stu-id="35dbc-111">Modern Authentication conversations (which are based on ADAL and OAuth 2.0) have some elements in common.</span></span>
  
- <span data-ttu-id="35dbc-112">用戶端需要資源的要求，在此情況下，用戶端是商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="35dbc-112">There is a client making a request for a resource, in this case, the client is Skype for Business.</span></span>
    
- <span data-ttu-id="35dbc-113">有一個資源可供用戶端需要特定的存取層級，而且此資源由目錄服務保護，在此情況下，資源是商務用 Skype Server。</span><span class="sxs-lookup"><span data-stu-id="35dbc-113">There is a resource to which the client needs a specific level of access, and this resource is secured by a directory service, in this case the resource is Skype for Business Server.</span></span>
    
- <span data-ttu-id="35dbc-114">有 OAuth 連線，也就是說，專門用來  *授權*  使用者存取資源的連線。</span><span class="sxs-lookup"><span data-stu-id="35dbc-114">There is an OAuth connection, in other words, a connection that is dedicated to  *authorizing*  a user to access a resource.</span></span> <span data-ttu-id="35dbc-115"> (OAuth 也是更具描述性的名稱「Server-to-Server ' 驗證，而且通常是 S2S 的縮寫。 ) </span><span class="sxs-lookup"><span data-stu-id="35dbc-115">(OAuth is also known by the more descriptive name, 'Server-to-Server' auth, and is often abbreviated as S2S.)</span></span>
    
<span data-ttu-id="35dbc-116">在商務用 Skype Server 新式驗證 (ADAL) 交談中，商務用 Skype Server 會在 Windows Server 2012 R2) 中透過 ADFS (ADFS 3.0 進行通訊。</span><span class="sxs-lookup"><span data-stu-id="35dbc-116">In Skype for Business Server Modern Authentication (ADAL) conversations, Skype for Business Server communicates through ADFS (ADFS 3.0 in Windows Server 2012 R2).</span></span> <span data-ttu-id="35dbc-117">驗證可能會使用其他一些身分識別提供者 (IdP) ，但商務用 Skype 伺服器必須設定為與 ADFS 直接通訊。</span><span class="sxs-lookup"><span data-stu-id="35dbc-117">The authentication may happen using some other Identity Provider (IdP), but Skype for Business server needs to be configured to communicate with ADFS, directly.</span></span> <span data-ttu-id="35dbc-118">如果您未設定 ADFS 搭配商務用 Skype Server，請完成 [ADFS 安裝](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd727938(v=ws.10))。</span><span class="sxs-lookup"><span data-stu-id="35dbc-118">If you haven't configured ADFS to work with Skype for Business Server please complete the [ADFS installation](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd727938(v=ws.10)).</span></span>
  
<span data-ttu-id="35dbc-119">ADAL 會包含在商務用 Skype Server 2015 的2016年3月累積更新，以及商務用 Skype 的2016三月份累積更新 **必須** 安裝，才能成功設定。</span><span class="sxs-lookup"><span data-stu-id="35dbc-119">ADAL is included in the March 2016 Cumulative Update for Skype for Business Server 2015, and the March 2016 Cumulative Update for Skype for Business **must** be installed and is needed for successful configuration.</span></span> <span data-ttu-id="35dbc-120">若為商務用 Skype Server 2019，可從產品的初始版本取得。</span><span class="sxs-lookup"><span data-stu-id="35dbc-120">For Skype for Business Server 2019, it is available from initial release of the product.</span></span>
  
> [!NOTE]
> <span data-ttu-id="35dbc-121">在初次發行時，只有在沒有任何混合的 Skype 拓撲涉及時，才支援內部部署環境中的新式驗證。</span><span class="sxs-lookup"><span data-stu-id="35dbc-121">During the initial release, Modern Authentication in an on-premises environment is supported only if there is no mixed Skype topology involved.</span></span> <span data-ttu-id="35dbc-122">例如，如果環境只是商務用 Skype Server。</span><span class="sxs-lookup"><span data-stu-id="35dbc-122">For example, if the environment is purely Skype for Business Server.</span></span> <span data-ttu-id="35dbc-123">此語句可能會變更。</span><span class="sxs-lookup"><span data-stu-id="35dbc-123">This statement may be subject to change.</span></span> 
  
<span data-ttu-id="35dbc-124">包含具有 ADAL 所使用之命令的 ps1 檔案的 PowerShell 套件，必須下載，以取得成功的設定。</span><span class="sxs-lookup"><span data-stu-id="35dbc-124">A PowerShell package including .ps1 files with the commands used by ADAL must be downloaded for successful configuration.</span></span>

<span data-ttu-id="35dbc-125">如需如何在商務用 Skype 中執行新式驗證的詳細資訊，請參閱： [如何使用現代驗證 (ADAL) 搭配商務用 skype](/microsoft-365/enterprise/hybrid-modern-auth-overview)</span><span class="sxs-lookup"><span data-stu-id="35dbc-125">For information on how to implement Modern Authentication in Skype for Business, please refer to: [How to use Modern Authentication (ADAL) with Skype for Business](/microsoft-365/enterprise/hybrid-modern-auth-overview)</span></span>