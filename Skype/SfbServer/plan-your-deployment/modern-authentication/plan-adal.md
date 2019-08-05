---
title: 使用商務用 Skype 規劃新式驗證 (ADAL)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: 本文說明什麼是現代驗證 (以 Active Directory 驗證庫 (ADAL) 和 OAuth 2.0) 為基礎。
ms.openlocfilehash: c984e2468e1735a46c5246806afc57dd67327990
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192980"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a><span data-ttu-id="f533e-103">如何在商務用 Skype 中使用新式驗證 (ADAL)</span><span class="sxs-lookup"><span data-stu-id="f533e-103">How to use Modern Authentication (ADAL) with Skype for Business</span></span>
 
<span data-ttu-id="f533e-104">本文將介紹現代驗證 (這是以 Active Directory 驗證庫 (ADAL) 和 OAuth 2.0) 為基礎的, 可在商務用 skype Server 2015 的商務用 Skype 的2016年3月累計更新中找到, 或從初始商務用 Skype Server 2019 的發行。</span><span class="sxs-lookup"><span data-stu-id="f533e-104">This article introduces Modern Authentication (which is based on the Active Directory Authentication Library (ADAL) and OAuth 2.0) that can be found in the March 2016 Cumulative Update for Skype for Business for Skype for Business Server 2015, or from initial release for Skype for Business Server 2019.</span></span>
  
## <a name="what-is-adal"></a><span data-ttu-id="f533e-105">什麼是 ADAL？</span><span class="sxs-lookup"><span data-stu-id="f533e-105">What is ADAL?</span></span>

<span data-ttu-id="f533e-106">ADAL 是「Active Directory 驗證文件庫」的縮寫, 以及 OAuth 2.0, 是新式驗證的基礎。</span><span class="sxs-lookup"><span data-stu-id="f533e-106">ADAL is the acronym for the 'Active Directory Authentication Library', and, along with OAuth 2.0, it is an underpinning of Modern Authentication.</span></span> <span data-ttu-id="f533e-107">這個程式碼庫的設計目的是為了讓您目錄中的安全資源可供用戶端應用程式 (例如商務用 Skype) 透過安全權杖使用。</span><span class="sxs-lookup"><span data-stu-id="f533e-107">This code library is designed to make secured resources in your directory available to client applications (like Skype for Business) via security tokens.</span></span> <span data-ttu-id="f533e-108">ADAL 可與 OAuth 2.0 搭配使用, 以啟用更多驗證與授權案例, 例如多重要素驗證 (MFA), 以及其他形式的 SAML 身分驗證。</span><span class="sxs-lookup"><span data-stu-id="f533e-108">ADAL works with OAuth 2.0 to enable more authentication and authorization scenarios, like Multi-factor Authentication (MFA), and more forms of SAML Auth.</span></span>
  
<span data-ttu-id="f533e-109">充當用戶端的各種應用程式都可以利用新式驗證來取得安全資源的協助。</span><span class="sxs-lookup"><span data-stu-id="f533e-109">A variety of apps that act as clients can leverage Modern Authentication for help in getting to secured resources.</span></span> <span data-ttu-id="f533e-110">在商務用 Skype Server 中, 此技術是在內部部署用戶端與內部部署伺服器之間使用, 以便為使用者提供適當的資源授權層級。</span><span class="sxs-lookup"><span data-stu-id="f533e-110">In Skype for Business Server, this technology is used between on-premises clients and on-premises servers in order to give users a proper level of authorization to resources.</span></span>
  
<span data-ttu-id="f533e-111">新式驗證交談 (以 ADAL 和 OAuth 2.0 為基礎) 有一些常見的元素。</span><span class="sxs-lookup"><span data-stu-id="f533e-111">Modern Authentication conversations (which are based on ADAL and OAuth 2.0) have some elements in common.</span></span>
  
- <span data-ttu-id="f533e-112">用戶端提出資源要求, 在此案例中, 用戶端是商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="f533e-112">There is a client making a request for a resource, in this case, the client is Skype for Business.</span></span>
    
- <span data-ttu-id="f533e-113">用戶端需要特定的存取層級, 而這個資源是由目錄服務來保護, 在此案例中, 資源是商務用 Skype Server。</span><span class="sxs-lookup"><span data-stu-id="f533e-113">There is a resource to which the client needs a specific level of access, and this resource is secured by a directory service, in this case the resource is Skype for Business Server.</span></span>
    
- <span data-ttu-id="f533e-114">有一個 OAuth 連線, 也就是一個專用來*授權*使用者存取資源的連線。</span><span class="sxs-lookup"><span data-stu-id="f533e-114">There is an OAuth connection, in other words, a connection that is dedicated to  *authorizing*  a user to access a resource.</span></span> <span data-ttu-id="f533e-115">(OAuth 也是由更具描述性的名稱 [伺服器到伺服器] 驗證, 通常縮寫為 S2S)。</span><span class="sxs-lookup"><span data-stu-id="f533e-115">(OAuth is also known by the more descriptive name, 'Server-to-Server' auth, and is often abbreviated as S2S.)</span></span>
    
<span data-ttu-id="f533e-116">在商務用 Skype Server 新式驗證 (ADAL) 交談中, 商務用 Skype 伺服器是透過 ADFS (在 Windows Server 2012 R2 中的 ADFS 3.0) 進行通訊。</span><span class="sxs-lookup"><span data-stu-id="f533e-116">In Skype for Business Server Modern Authentication (ADAL) conversations, Skype for Business Server communicates through ADFS (ADFS 3.0 in Windows Server 2012 R2).</span></span> <span data-ttu-id="f533e-117">驗證可能會使用一些其他身分識別提供者 (IdP) 進行, 但商務用 Skype 伺服器必須設定為與 ADFS 直接通訊。</span><span class="sxs-lookup"><span data-stu-id="f533e-117">The authentication may happen using some other Identity Provider (IdP), but Skype for Business server needs to be configured to communicate with ADFS, directly.</span></span> <span data-ttu-id="f533e-118">如果您尚未將 ADFS 設定為與商務用 Skype 伺服器搭配使用, 請完成[ADFS 安裝](https://technet.microsoft.com/en-us/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="f533e-118">If you haven't configured ADFS to work with Skype for Business Server please complete the [ADFS installation](https://technet.microsoft.com/en-us/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx).</span></span>
  
<span data-ttu-id="f533e-119">在商務用 Skype Server 2015 的2016年3月累計更新中, 且**必須**安裝適用于商務用 skype 的年 3 2016 月累計更新, 才能成功進行設定。</span><span class="sxs-lookup"><span data-stu-id="f533e-119">ADAL is included in the March 2016 Cumulative Update for Skype for Business Server 2015, and the March 2016 Cumulative Update for Skype for Business **must** be installed and is needed for successful configuration.</span></span> <span data-ttu-id="f533e-120">如果是商務用 Skype Server 2019, 就可以從產品初次發行中取得。</span><span class="sxs-lookup"><span data-stu-id="f533e-120">For Skype for Business Server 2019, it is available from initial release of the product.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f533e-121">在初始發行期間, 只有在沒有任何混合 Skype 拓撲涉及的情況下, 才支援內部部署環境中的新式驗證。</span><span class="sxs-lookup"><span data-stu-id="f533e-121">During the initial release, Modern Authentication in an on-premises environment is supported only if there is no mixed Skype topology involved.</span></span> <span data-ttu-id="f533e-122">例如, 如果環境是純粹的商務用 Skype 伺服器。</span><span class="sxs-lookup"><span data-stu-id="f533e-122">For example, if the environment is purely Skype for Business Server.</span></span> <span data-ttu-id="f533e-123">此語句可能受變更。</span><span class="sxs-lookup"><span data-stu-id="f533e-123">This statement may be subject to change.</span></span> 
  
<span data-ttu-id="f533e-124">您必須下載包含在 ADAL 中使用之命令的 PowerShell 套件 (包括 ps1 檔案), 才能成功進行設定。</span><span class="sxs-lookup"><span data-stu-id="f533e-124">A PowerShell package including .ps1 files with the commands used by ADAL must be downloaded for successful configuration.</span></span>

<span data-ttu-id="f533e-125">如需如何在商務用 Skype 中實施新式驗證的詳細資訊, 請參閱:[如何在商務用 skype 中使用新式驗證 (ADAL)](../../manage/authentication/use-adal.md)</span><span class="sxs-lookup"><span data-stu-id="f533e-125">For information on how to implement Modern Authentication in Skype for Business, please refer to: [How to use Modern Authentication (ADAL) with Skype for Business](../../manage/authentication/use-adal.md)</span></span>
