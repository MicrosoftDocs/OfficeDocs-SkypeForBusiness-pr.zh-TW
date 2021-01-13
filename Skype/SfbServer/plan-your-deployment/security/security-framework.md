---
title: 商務用 Skype Server 的安全性架構
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 01131e28-b38e-40d9-8524-06725b9c6608
description: 本節概述構成商務用 Skype Server 安全性框架的基本元素。 瞭解這些元素的運作方式，對於在保護特定商務用 Skype Server 部署的相關決策方面是必要的。
ms.openlocfilehash: 94d2ffac30e029ab6631557a69d6da3ec108657f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832093"
---
# <a name="security-framework-for-skype-for-business-server"></a><span data-ttu-id="62b42-104">商務用 Skype Server 的安全性架構</span><span class="sxs-lookup"><span data-stu-id="62b42-104">Security framework for Skype for Business Server</span></span>
 
<span data-ttu-id="62b42-105">本節概述構成商務用 Skype Server 安全性框架的基本元素。</span><span class="sxs-lookup"><span data-stu-id="62b42-105">This section provides an overview of the fundamental elements that form the security framework for Skype for Business Server.</span></span> <span data-ttu-id="62b42-106">瞭解這些元素的運作方式，對於在保護特定商務用 Skype Server 部署的相關決策方面是必要的。</span><span class="sxs-lookup"><span data-stu-id="62b42-106">Understanding how these elements work together is essential to making informed decisions about securing your particular Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="62b42-107">這些元素如下：</span><span class="sxs-lookup"><span data-stu-id="62b42-107">These elements are as follows:</span></span>
  
- <span data-ttu-id="62b42-108">Active Directory 網域服務 (AD DS) 提供使用者帳戶和網路資源的單一信任後端存放庫。</span><span class="sxs-lookup"><span data-stu-id="62b42-108">Active Directory Domain Services (AD DS) provides a single trusted back-end repository for user accounts and network resources.</span></span>
    
- <span data-ttu-id="62b42-109">Role-Based 存取控制 (RBAC) 可讓您委派管理工作，同時維持高安全性標準。</span><span class="sxs-lookup"><span data-stu-id="62b42-109">Role-Based Access Control (RBAC) enables you to delegate administrative tasks while maintaining high standards for security.</span></span>
    
- <span data-ttu-id="62b42-110">公開金鑰基礎結構 (PKI) 會使用受信任的憑證授權單位單位 (CAs) 所發行的憑證，以驗證服務器並確保資料完整性。</span><span class="sxs-lookup"><span data-stu-id="62b42-110">Public Key Infrastructure (PKI) uses certificates issued by trusted certification authorities (CAs) to authenticate servers and ensure data integrity.</span></span>
    
- <span data-ttu-id="62b42-111">傳輸層安全性 (TLS) 、HTTPS over SSL (HTTPS) ，以及相互 TLS (MTLS) 啟用端點驗證和 IM 加密。</span><span class="sxs-lookup"><span data-stu-id="62b42-111">Transport Layer Security (TLS), HTTPS over SSL (HTTPS), and mutual TLS (MTLS) enable endpoint authentication and IM encryption.</span></span> <span data-ttu-id="62b42-112">使用安全 Real-Time 傳輸通訊協定 (SRTP) ，對點對點音訊、影片和應用程式共用資料流程進行加密。</span><span class="sxs-lookup"><span data-stu-id="62b42-112">Point-to-point audio, video, and application sharing streams are encrypted using Secure Real-Time Transport Protocol (SRTP).</span></span>
    
- <span data-ttu-id="62b42-113">適用于使用者驗證的業界標準通訊協定。</span><span class="sxs-lookup"><span data-stu-id="62b42-113">Industry-standard protocols for user authentication, where possible.</span></span>
    
- <span data-ttu-id="62b42-114">Windows PowerShell 提供預設啟用的安全性功能，讓使用者無法輕易或無意中執行腳本。</span><span class="sxs-lookup"><span data-stu-id="62b42-114">Windows PowerShell provides security features that are enabled by default so that users cannot easily or unknowingly run scripts.</span></span>
    
<span data-ttu-id="62b42-115">這些基本的安全性元素共同運作，以定義信任的使用者、伺服器、連線和作業，以協助確保商務用 Skype Server 的安全基礎。</span><span class="sxs-lookup"><span data-stu-id="62b42-115">These fundamental security elements work together to define trusted users, servers, connections, and operations to help ensure a secure foundation for Skype for Business Server.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="62b42-116">本節內容</span><span class="sxs-lookup"><span data-stu-id="62b42-116">In this section</span></span>

<span data-ttu-id="62b42-117">本節中的主題說明這些基本元素的運作方式，以增強商務用 Skype 伺服器基礎結構的安全性。</span><span class="sxs-lookup"><span data-stu-id="62b42-117">The topics in this section describe how each of these fundamental elements works to enhance the security of your Skype for Business Server infrastructure.</span></span>
  
- [<span data-ttu-id="62b42-118">商務用 Skype Server 的 Active Directory 網域服務</span><span class="sxs-lookup"><span data-stu-id="62b42-118">Active Directory Domain Services for Skype for Business Server</span></span>](active-directory-domain-services.md)
    
- [<span data-ttu-id="62b42-119">商務用 Skype Server (RBAC) 角色的存取控制</span><span class="sxs-lookup"><span data-stu-id="62b42-119">Role-based access control (RBAC) for Skype for Business Server</span></span>](role-based-access-control-rbac.md)
    
- [<span data-ttu-id="62b42-120">商務用 Skype Server 的公用機碼基礎結構</span><span class="sxs-lookup"><span data-stu-id="62b42-120">Public Key Infrastructure for Skype for Business Server</span></span>](public-key-infrastructure-for-skype.md)
    
- [<span data-ttu-id="62b42-121">適用于商務用 Skype Server 的 TLS 及 MTLS</span><span class="sxs-lookup"><span data-stu-id="62b42-121">TLS and MTLS for Skype for Business Server</span></span>](tls-and-mtls.md)
    
- [<span data-ttu-id="62b42-122">商務用 Skype Server 的加密</span><span class="sxs-lookup"><span data-stu-id="62b42-122">Encryption for Skype for Business Server</span></span>](encryption.md)
    
- [<span data-ttu-id="62b42-123">商務用 Skype Server 的使用者和用戶端驗證</span><span class="sxs-lookup"><span data-stu-id="62b42-123">User and client authentication for Skype for Business Server</span></span>](user-and-client-authentication.md)
    
- [<span data-ttu-id="62b42-124">Windows PowerShell 和商務用 Skype Server 管理工具</span><span class="sxs-lookup"><span data-stu-id="62b42-124">Windows PowerShell and Skype for Business Server management tools</span></span>](management-tools.md)
    

