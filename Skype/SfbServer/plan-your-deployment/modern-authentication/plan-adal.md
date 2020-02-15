---
title: 規劃新式驗證 (ADAL) 與 Skype for Business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 本文說明新式驗證 （也就根據 Active Directory Authentication Library (ADAL) 和 OAuth 2.0） 的功能。
ms.openlocfilehash: 5a51b0712f33cbafc64f87f56b4d12649bfad97e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046286"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a><span data-ttu-id="4771e-103">如何使用商務用 Skype 新式驗證 (ADAL)</span><span class="sxs-lookup"><span data-stu-id="4771e-103">How to use Modern Authentication (ADAL) with Skype for Business</span></span>
 
<span data-ttu-id="4771e-104">本文介紹新式驗證 （也就根據 Active Directory Authentication Library (ADAL) 和 OAuth 2.0） 可以找到年 3 月 2016年中的商務用 Skype Server 2015，或是從初始的商務用 Skype 的累計更新skype for Business Server 2019 的版本。</span><span class="sxs-lookup"><span data-stu-id="4771e-104">This article introduces Modern Authentication (which is based on the Active Directory Authentication Library (ADAL) and OAuth 2.0) that can be found in the March 2016 Cumulative Update for Skype for Business for Skype for Business Server 2015, or from initial release for Skype for Business Server 2019.</span></span>
  
## <a name="what-is-adal"></a><span data-ttu-id="4771e-105">ADAL 是什麼？</span><span class="sxs-lookup"><span data-stu-id="4771e-105">What is ADAL?</span></span>

<span data-ttu-id="4771e-106">ADAL 是縮寫 'Active Directory 驗證程式庫'，而且，以及 OAuth 2.0 的新式驗證加強。</span><span class="sxs-lookup"><span data-stu-id="4771e-106">ADAL is the acronym for the 'Active Directory Authentication Library', and, along with OAuth 2.0, it is an underpinning of Modern Authentication.</span></span> <span data-ttu-id="4771e-107">此程式碼文件庫被為了讓您的目錄中的安全的資源可供用戶端應用程式 （例如商務用 Skype) 透過安全性權杖。</span><span class="sxs-lookup"><span data-stu-id="4771e-107">This code library is designed to make secured resources in your directory available to client applications (like Skype for Business) via security tokens.</span></span> <span data-ttu-id="4771e-108">ADAL 搭配 OAuth 2.0，以啟用多個驗證和授權案例，像是多重要素驗證 (MFA)，以及更多的表單的 SAML 驗證]。</span><span class="sxs-lookup"><span data-stu-id="4771e-108">ADAL works with OAuth 2.0 to enable more authentication and authorization scenarios, like Multi-factor Authentication (MFA), and more forms of SAML Auth.</span></span>
  
<span data-ttu-id="4771e-109">各種作為用戶端可以利用新式驗證，以協助易於存取的應用程式的安全資源。</span><span class="sxs-lookup"><span data-stu-id="4771e-109">A variety of apps that act as clients can leverage Modern Authentication for help in getting to secured resources.</span></span> <span data-ttu-id="4771e-110">Skype for Business Server，這項技術用於內部用戶端與內部部署伺服器之間才能讓使用者能夠適當層級的資源的授權。</span><span class="sxs-lookup"><span data-stu-id="4771e-110">In Skype for Business Server, this technology is used between on-premises clients and on-premises servers in order to give users a proper level of authorization to resources.</span></span>
  
<span data-ttu-id="4771e-111">新式驗證交談 （也就根據 ADAL 和 OAuth 2.0） 有共同的一些項目。</span><span class="sxs-lookup"><span data-stu-id="4771e-111">Modern Authentication conversations (which are based on ADAL and OAuth 2.0) have some elements in common.</span></span>
  
- <span data-ttu-id="4771e-112">沒有提出資源要求用戶端，在此情況下，用戶端是商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="4771e-112">There is a client making a request for a resource, in this case, the client is Skype for Business.</span></span>
    
- <span data-ttu-id="4771e-113">要在用戶端需要特定權限等級，資源和此資源會受到目錄服務，在此情況下資源時 Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="4771e-113">There is a resource to which the client needs a specific level of access, and this resource is secured by a directory service, in this case the resource is Skype for Business Server.</span></span>
    
- <span data-ttu-id="4771e-114">有了 OAuth 連線，也就是說，連線，則專用於*授權*使用者存取資源。</span><span class="sxs-lookup"><span data-stu-id="4771e-114">There is an OAuth connection, in other words, a connection that is dedicated to  *authorizing*  a user to access a resource.</span></span> <span data-ttu-id="4771e-115">（OAuth 更具描述性的名稱，' 伺服器對伺服器 ' 驗證，也已知的而且通常會縮寫成 S2S）。</span><span class="sxs-lookup"><span data-stu-id="4771e-115">(OAuth is also known by the more descriptive name, 'Server-to-Server' auth, and is often abbreviated as S2S.)</span></span>
    
<span data-ttu-id="4771e-116">Skype for Business Server 新式驗證 (ADAL) 交談，Skype for Business Server 會透過 ADFS (在 Windows Server 2012 R2 的 ADFS 3.0) 進行通訊。</span><span class="sxs-lookup"><span data-stu-id="4771e-116">In Skype for Business Server Modern Authentication (ADAL) conversations, Skype for Business Server communicates through ADFS (ADFS 3.0 in Windows Server 2012 R2).</span></span> <span data-ttu-id="4771e-117">驗證也可能會使用某些其他身分識別提供者 (Isp)，但 Skype for Business server 必須經過設定才能使用 ADFS，直接通訊。</span><span class="sxs-lookup"><span data-stu-id="4771e-117">The authentication may happen using some other Identity Provider (IdP), but Skype for Business server needs to be configured to communicate with ADFS, directly.</span></span> <span data-ttu-id="4771e-118">如果您還沒有設定為搭配 Skype for Business Server ADFS 請完成[ADFS 安裝](https://technet.microsoft.com/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="4771e-118">If you haven't configured ADFS to work with Skype for Business Server please complete the [ADFS installation](https://technet.microsoft.com/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx).</span></span>
  
<span data-ttu-id="4771e-119">ADAL 隨附於年 3 月 2016年累計更新用於商務用 Skype Server 2015 及年 3 月 2016年的 Skype for Business**必須**累計更新安裝，且需要成功設定。</span><span class="sxs-lookup"><span data-stu-id="4771e-119">ADAL is included in the March 2016 Cumulative Update for Skype for Business Server 2015, and the March 2016 Cumulative Update for Skype for Business **must** be installed and is needed for successful configuration.</span></span> <span data-ttu-id="4771e-120">Skype 商務 Server 2019，它是來自最初發行版本的產品。</span><span class="sxs-lookup"><span data-stu-id="4771e-120">For Skype for Business Server 2019, it is available from initial release of the product.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4771e-121">期間最初發行版本中，如果有任何混合的 Skype 拓樸的相關支援在內部部署環境中的新式驗證。</span><span class="sxs-lookup"><span data-stu-id="4771e-121">During the initial release, Modern Authentication in an on-premises environment is supported only if there is no mixed Skype topology involved.</span></span> <span data-ttu-id="4771e-122">例如，如果環境是純粹 Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="4771e-122">For example, if the environment is purely Skype for Business Server.</span></span> <span data-ttu-id="4771e-123">這個陳述式可能會受到變更。</span><span class="sxs-lookup"><span data-stu-id="4771e-123">This statement may be subject to change.</span></span> 
  
<span data-ttu-id="4771e-124">成功設定必須下載 PowerShell 封裝.ps1 檔案包括具有 ADAL 所使用的命令。</span><span class="sxs-lookup"><span data-stu-id="4771e-124">A PowerShell package including .ps1 files with the commands used by ADAL must be downloaded for successful configuration.</span></span>

<span data-ttu-id="4771e-125">如需如何在商務用 Skype 中實作的新式驗證資訊，請參閱：[如何使用新式驗證 (ADAL) 與商務用 Skype](../../manage/authentication/use-adal.md)</span><span class="sxs-lookup"><span data-stu-id="4771e-125">For information on how to implement Modern Authentication in Skype for Business, please refer to: [How to use Modern Authentication (ADAL) with Skype for Business](../../manage/authentication/use-adal.md)</span></span>
