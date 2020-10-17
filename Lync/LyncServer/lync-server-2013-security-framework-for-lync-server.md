---
title: Lync Server 2013： Lync Server 的安全性框架
description: Lync Server 2013： Lync Server 的安全性框架。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Security framework for Lync Server 2013
ms:assetid: 01131e28-b38e-40d9-8524-06725b9c6608
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481316(v=OCS.15)
ms:contentKeyID: 59893866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d30c26929ddedbf653abd1fc353b6873ad8f36f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551429"
---
# <a name="security-framework-for-lync-server-2013"></a><span data-ttu-id="216b4-103">Lync Server 2013 的安全性框架</span><span class="sxs-lookup"><span data-stu-id="216b4-103">Security framework for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="216b4-104">_**主題上次修改日期：** 2013-11-08_</span><span class="sxs-lookup"><span data-stu-id="216b4-104">_**Topic Last Modified:** 2013-11-08_</span></span>

<span data-ttu-id="216b4-105">本節提供組成 Microsoft Lync Server 2013 安全性框架之基礎元素的概述。</span><span class="sxs-lookup"><span data-stu-id="216b4-105">This section provides an overview of the fundamental elements that form the security framework for Microsoft Lync Server 2013.</span></span> <span data-ttu-id="216b4-106">瞭解這些元素的運作方式，對於在保護特定 Lync Server 2013 部署的相關決策方面是必要的。</span><span class="sxs-lookup"><span data-stu-id="216b4-106">Understanding how these elements work together is essential to making informed decisions about securing your particular Lync Server 2013 deployment.</span></span>

<span data-ttu-id="216b4-107">這些元素如下：</span><span class="sxs-lookup"><span data-stu-id="216b4-107">These elements are as follows:</span></span>

  - <span data-ttu-id="216b4-108">Active Directory 網域服務 (AD DS) 提供使用者帳戶和網路資源的單一信任後端存放庫。</span><span class="sxs-lookup"><span data-stu-id="216b4-108">Active Directory Domain Services (AD DS) provides a single trusted back-end repository for user accounts and network resources.</span></span>

  - <span data-ttu-id="216b4-109">Role-Based 存取控制 (RBAC) 可讓您委派管理工作，同時維持高安全性標準。</span><span class="sxs-lookup"><span data-stu-id="216b4-109">Role-Based Access Control (RBAC) enables you to delegate administrative tasks while maintaining high standards for security.</span></span>

  - <span data-ttu-id="216b4-110">公開金鑰基礎結構 (PKI) 會使用受信任的憑證授權單位單位 (CAs) 所發行的憑證，以驗證服務器並確保資料完整性。</span><span class="sxs-lookup"><span data-stu-id="216b4-110">Public Key Infrastructure (PKI) uses certificates issued by trusted certification authorities (CAs) to authenticate servers and ensure data integrity.</span></span>

  - <span data-ttu-id="216b4-111">傳輸層安全性 (TLS) 、HTTPS over SSL (HTTPS) ，以及相互 TLS (MTLS) 啟用端點驗證和 IM 加密。</span><span class="sxs-lookup"><span data-stu-id="216b4-111">Transport Layer Security (TLS), HTTPS over SSL (HTTPS), and mutual TLS (MTLS) enable endpoint authentication and IM encryption.</span></span> <span data-ttu-id="216b4-112">使用安全 Real-Time 傳輸通訊協定 (SRTP) ，對點對點音訊、影片和應用程式共用資料流程進行加密。</span><span class="sxs-lookup"><span data-stu-id="216b4-112">Point-to-point audio, video, and application sharing streams are encrypted using Secure Real-Time Transport Protocol (SRTP).</span></span>

  - <span data-ttu-id="216b4-113">適用于使用者驗證的業界標準通訊協定。</span><span class="sxs-lookup"><span data-stu-id="216b4-113">Industry-standard protocols for user authentication, where possible.</span></span>

  - <span data-ttu-id="216b4-114">Windows PowerShell 提供預設啟用的安全性功能，讓使用者無法輕易或無意中執行腳本。</span><span class="sxs-lookup"><span data-stu-id="216b4-114">Windows PowerShell provides security features that are enabled by default so that users cannot easily or unknowingly run scripts.</span></span>

<span data-ttu-id="216b4-115">這些基本的安全性元素共同運作，以定義信任的使用者、伺服器、連線和作業，以協助確保 Lync Server 2013 的安全基礎。</span><span class="sxs-lookup"><span data-stu-id="216b4-115">These fundamental security elements work together to define trusted users, servers, connections, and operations to help ensure a secure foundation for Lync Server 2013.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="216b4-116">本章節內容</span><span class="sxs-lookup"><span data-stu-id="216b4-116">In This Section</span></span>

<span data-ttu-id="216b4-117">本節中的主題說明這些基本元素的運作方式，以加強 Lync Server 基礎結構的安全性。</span><span class="sxs-lookup"><span data-stu-id="216b4-117">The topics in this section describe how each of these fundamental elements works to enhance the security of your Lync Server infrastructure.</span></span>

  - [<span data-ttu-id="216b4-118">Lync Server 2013 的 Active Directory 網域服務</span><span class="sxs-lookup"><span data-stu-id="216b4-118">Active Directory Domain Services for Lync Server 2013</span></span>](lync-server-2013-active-directory-domain-services-for-lync-server.md)

  - [<span data-ttu-id="216b4-119">Lync Server 2013 的以角色為基礎的存取控制 (RBAC) </span><span class="sxs-lookup"><span data-stu-id="216b4-119">Role-based access control (RBAC) for Lync Server 2013</span></span>](lync-server-2013-role-based-access-control-rbac.md)

  - [<span data-ttu-id="216b4-120">Lync Server 2013 的公用機碼基礎結構</span><span class="sxs-lookup"><span data-stu-id="216b4-120">Public Key Infrastructure for Lync Server 2013</span></span>](lync-server-2013-public-key-infrastructure.md)

  - [<span data-ttu-id="216b4-121">Lync Server 2013 的 TLS 和 MTLS</span><span class="sxs-lookup"><span data-stu-id="216b4-121">TLS and MTLS for Lync Server 2013</span></span>](lync-server-2013-tls-and-mtls.md)

  - [<span data-ttu-id="216b4-122">Lync Server 2013 的加密</span><span class="sxs-lookup"><span data-stu-id="216b4-122">Encryption for Lync Server 2013</span></span>](lync-server-2013-encryption.md)

  - [<span data-ttu-id="216b4-123">Lync Server 2013 的使用者和用戶端驗證</span><span class="sxs-lookup"><span data-stu-id="216b4-123">User and client authentication for Lync Server 2013</span></span>](lync-server-2013-user-and-client-authentication.md)

  - [<span data-ttu-id="216b4-124">Windows PowerShell 和 Lync Server 2013 管理工具</span><span class="sxs-lookup"><span data-stu-id="216b4-124">Windows PowerShell and Lync Server 2013 management tools</span></span>](lync-server-2013-windows-powershell-and-lync-server-management-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

