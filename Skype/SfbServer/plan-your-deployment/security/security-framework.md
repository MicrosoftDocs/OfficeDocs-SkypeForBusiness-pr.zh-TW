---
title: 商務用 Skype Server 的安全性架構
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 01131e28-b38e-40d9-8524-06725b9c6608
description: 本節概要說明構成商務用 Skype Server 安全架構的基本元素。 瞭解這些元素的運作方式，對於保證您特定的商務用 Skype Server 部署的安全決策是必要的。
ms.openlocfilehash: 432d4cda013e5bdec2613e3c9052f10b7d619302
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815611"
---
# <a name="security-framework-for-skype-for-business-server"></a><span data-ttu-id="52648-104">商務用 Skype Server 的安全性架構</span><span class="sxs-lookup"><span data-stu-id="52648-104">Security framework for Skype for Business Server</span></span>
 
<span data-ttu-id="52648-105">本節概要說明構成商務用 Skype Server 安全架構的基本元素。</span><span class="sxs-lookup"><span data-stu-id="52648-105">This section provides an overview of the fundamental elements that form the security framework for Skype for Business Server.</span></span> <span data-ttu-id="52648-106">瞭解這些元素的運作方式，對於保證您特定的商務用 Skype Server 部署的安全決策是必要的。</span><span class="sxs-lookup"><span data-stu-id="52648-106">Understanding how these elements work together is essential to making informed decisions about securing your particular Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="52648-107">這些元素如下所示：</span><span class="sxs-lookup"><span data-stu-id="52648-107">These elements are as follows:</span></span>
  
- <span data-ttu-id="52648-108">Active Directory 網域服務（AD DS）為使用者帳戶和網路資源提供單一受信任的後端儲備庫。</span><span class="sxs-lookup"><span data-stu-id="52648-108">Active Directory Domain Services (AD DS) provides a single trusted back-end repository for user accounts and network resources.</span></span>
    
- <span data-ttu-id="52648-109">角色式存取控制（RBAC）可讓您委派管理工作，同時維持高安全性的標準。</span><span class="sxs-lookup"><span data-stu-id="52648-109">Role-Based Access Control (RBAC) enables you to delegate administrative tasks while maintaining high standards for security.</span></span>
    
- <span data-ttu-id="52648-110">公開金鑰基礎結構（PKI）使用受信任的憑證授權單位（Ca）所頒發的憑證來驗證服務器並確保資料完整性。</span><span class="sxs-lookup"><span data-stu-id="52648-110">Public Key Infrastructure (PKI) uses certificates issued by trusted certification authorities (CAs) to authenticate servers and ensure data integrity.</span></span>
    
- <span data-ttu-id="52648-111">傳輸層安全性（TLS）、經由 SSL （HTTPS）的 HTTPS 以及相互 TLS （MTLS）啟用端點驗證與 IM 加密。</span><span class="sxs-lookup"><span data-stu-id="52648-111">Transport Layer Security (TLS), HTTPS over SSL (HTTPS), and mutual TLS (MTLS) enable endpoint authentication and IM encryption.</span></span> <span data-ttu-id="52648-112">使用安全的即時傳輸通訊協定（SRTP）來加密點對點音訊、影片和應用程式共用資料流程。</span><span class="sxs-lookup"><span data-stu-id="52648-112">Point-to-point audio, video, and application sharing streams are encrypted using Secure Real-Time Transport Protocol (SRTP).</span></span>
    
- <span data-ttu-id="52648-113">使用者驗證的工業標準通訊協定（如果可能）。</span><span class="sxs-lookup"><span data-stu-id="52648-113">Industry-standard protocols for user authentication, where possible.</span></span>
    
- <span data-ttu-id="52648-114">Windows PowerShell 提供預設啟用的安全性功能，讓使用者不會輕易或無意中執行腳本。</span><span class="sxs-lookup"><span data-stu-id="52648-114">Windows PowerShell provides security features that are enabled by default so that users cannot easily or unknowingly run scripts.</span></span>
    
<span data-ttu-id="52648-115">這些基本的安全性元素共同運作，以定義受信任的使用者、伺服器、連線及作業，以協助確保商務用 Skype Server 的安全基礎。</span><span class="sxs-lookup"><span data-stu-id="52648-115">These fundamental security elements work together to define trusted users, servers, connections, and operations to help ensure a secure foundation for Skype for Business Server.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="52648-116">本節內容</span><span class="sxs-lookup"><span data-stu-id="52648-116">In this section</span></span>

<span data-ttu-id="52648-117">本節中的主題描述這些基本元素的運作方式，以增強商務用 Skype Server 基礎結構的安全性。</span><span class="sxs-lookup"><span data-stu-id="52648-117">The topics in this section describe how each of these fundamental elements works to enhance the security of your Skype for Business Server infrastructure.</span></span>
  
- [<span data-ttu-id="52648-118">商務用 Skype Server 的 Active Directory 網域服務</span><span class="sxs-lookup"><span data-stu-id="52648-118">Active Directory Domain Services for Skype for Business Server</span></span>](active-directory-domain-services.md)
    
- [<span data-ttu-id="52648-119">商務用 Skype Server 的以角色為基礎的存取控制（RBAC）</span><span class="sxs-lookup"><span data-stu-id="52648-119">Role-based access control (RBAC) for Skype for Business Server</span></span>](role-based-access-control-rbac.md)
    
- [<span data-ttu-id="52648-120">商務用 Skype Server 的公開金鑰基礎結構</span><span class="sxs-lookup"><span data-stu-id="52648-120">Public Key Infrastructure for Skype for Business Server</span></span>](public-key-infrastructure-for-skype.md)
    
- [<span data-ttu-id="52648-121">商務用 Skype Server 的 TLS 和 MTLS</span><span class="sxs-lookup"><span data-stu-id="52648-121">TLS and MTLS for Skype for Business Server</span></span>](tls-and-mtls.md)
    
- [<span data-ttu-id="52648-122">商務用 Skype Server 的加密</span><span class="sxs-lookup"><span data-stu-id="52648-122">Encryption for Skype for Business Server</span></span>](encryption.md)
    
- [<span data-ttu-id="52648-123">商務用 Skype Server 的使用者和用戶端驗證</span><span class="sxs-lookup"><span data-stu-id="52648-123">User and client authentication for Skype for Business Server</span></span>](user-and-client-authentication.md)
    
- [<span data-ttu-id="52648-124">Windows PowerShell 和商務用 Skype Server 管理工具</span><span class="sxs-lookup"><span data-stu-id="52648-124">Windows PowerShell and Skype for Business Server management tools</span></span>](management-tools.md)
    

