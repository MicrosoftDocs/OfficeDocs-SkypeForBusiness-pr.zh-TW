---
title: Lync Server 2013： Lync Server 的安全性架構
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Security framework for Lync Server 2013
ms:assetid: 01131e28-b38e-40d9-8524-06725b9c6608
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481316(v=OCS.15)
ms:contentKeyID: 59893866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17900e0ca9db8f9dbc1bf66a1bd65aff62d9dd62
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982735"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="security-framework-for-lync-server-2013"></a><span data-ttu-id="4e2d6-102">Lync Server 2013 的安全性架構</span><span class="sxs-lookup"><span data-stu-id="4e2d6-102">Security framework for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4e2d6-103">_**主題上次修改日期：** 2013-11-08_</span><span class="sxs-lookup"><span data-stu-id="4e2d6-103">_**Topic Last Modified:** 2013-11-08_</span></span>

<span data-ttu-id="4e2d6-104">本節概要說明構成 Microsoft Lync Server 2013 安全性架構的基本元素。</span><span class="sxs-lookup"><span data-stu-id="4e2d6-104">This section provides an overview of the fundamental elements that form the security framework for Microsoft Lync Server 2013.</span></span> <span data-ttu-id="4e2d6-105">瞭解這些元素共同運作的方式，對於保證您的特定 Lync Server 2013 部署的相關決策是必要的。</span><span class="sxs-lookup"><span data-stu-id="4e2d6-105">Understanding how these elements work together is essential to making informed decisions about securing your particular Lync Server 2013 deployment.</span></span>

<span data-ttu-id="4e2d6-106">這些元素如下所示：</span><span class="sxs-lookup"><span data-stu-id="4e2d6-106">These elements are as follows:</span></span>

  - <span data-ttu-id="4e2d6-107">Active Directory 網域服務（AD DS）為使用者帳戶和網路資源提供單一受信任的後端儲備庫。</span><span class="sxs-lookup"><span data-stu-id="4e2d6-107">Active Directory Domain Services (AD DS) provides a single trusted back-end repository for user accounts and network resources.</span></span>

  - <span data-ttu-id="4e2d6-108">角色式存取控制（RBAC）可讓您委派管理工作，同時維持高安全性的標準。</span><span class="sxs-lookup"><span data-stu-id="4e2d6-108">Role-Based Access Control (RBAC) enables you to delegate administrative tasks while maintaining high standards for security.</span></span>

  - <span data-ttu-id="4e2d6-109">公開金鑰基礎結構（PKI）使用受信任的憑證授權單位（Ca）所頒發的憑證來驗證服務器並確保資料完整性。</span><span class="sxs-lookup"><span data-stu-id="4e2d6-109">Public Key Infrastructure (PKI) uses certificates issued by trusted certification authorities (CAs) to authenticate servers and ensure data integrity.</span></span>

  - <span data-ttu-id="4e2d6-110">傳輸層安全性（TLS）、經由 SSL （HTTPS）的 HTTPS 以及相互 TLS （MTLS）啟用端點驗證與 IM 加密。</span><span class="sxs-lookup"><span data-stu-id="4e2d6-110">Transport Layer Security (TLS), HTTPS over SSL (HTTPS), and mutual TLS (MTLS) enable endpoint authentication and IM encryption.</span></span> <span data-ttu-id="4e2d6-111">使用安全的即時傳輸通訊協定（SRTP）來加密點對點音訊、影片和應用程式共用資料流程。</span><span class="sxs-lookup"><span data-stu-id="4e2d6-111">Point-to-point audio, video, and application sharing streams are encrypted using Secure Real-Time Transport Protocol (SRTP).</span></span>

  - <span data-ttu-id="4e2d6-112">使用者驗證的工業標準通訊協定（如果可能）。</span><span class="sxs-lookup"><span data-stu-id="4e2d6-112">Industry-standard protocols for user authentication, where possible.</span></span>

  - <span data-ttu-id="4e2d6-113">Windows PowerShell 提供預設啟用的安全性功能，讓使用者不會輕易或無意中執行腳本。</span><span class="sxs-lookup"><span data-stu-id="4e2d6-113">Windows PowerShell provides security features that are enabled by default so that users cannot easily or unknowingly run scripts.</span></span>

<span data-ttu-id="4e2d6-114">這些基本的安全性元素共同運作，以定義受信任的使用者、伺服器、連線及作業，以協助確保 Lync Server 2013 的安全基礎。</span><span class="sxs-lookup"><span data-stu-id="4e2d6-114">These fundamental security elements work together to define trusted users, servers, connections, and operations to help ensure a secure foundation for Lync Server 2013.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4e2d6-115">本節內容</span><span class="sxs-lookup"><span data-stu-id="4e2d6-115">In This Section</span></span>

<span data-ttu-id="4e2d6-116">本節中的主題描述這些基本元素的運作方式，以增強 Lync Server 基礎結構的安全性。</span><span class="sxs-lookup"><span data-stu-id="4e2d6-116">The topics in this section describe how each of these fundamental elements works to enhance the security of your Lync Server infrastructure.</span></span>

  - [<span data-ttu-id="4e2d6-117">Lync Server 2013 的 Active Directory 網域服務</span><span class="sxs-lookup"><span data-stu-id="4e2d6-117">Active Directory Domain Services for Lync Server 2013</span></span>](lync-server-2013-active-directory-domain-services-for-lync-server.md)

  - [<span data-ttu-id="4e2d6-118">Lync Server 2013 的角色式存取控制（RBAC）</span><span class="sxs-lookup"><span data-stu-id="4e2d6-118">Role-based access control (RBAC) for Lync Server 2013</span></span>](lync-server-2013-role-based-access-control-rbac.md)

  - [<span data-ttu-id="4e2d6-119">Lync Server 2013 的公開金鑰基礎結構</span><span class="sxs-lookup"><span data-stu-id="4e2d6-119">Public Key Infrastructure for Lync Server 2013</span></span>](lync-server-2013-public-key-infrastructure.md)

  - [<span data-ttu-id="4e2d6-120">Lync Server 2013 的 TLS 和 MTLS</span><span class="sxs-lookup"><span data-stu-id="4e2d6-120">TLS and MTLS for Lync Server 2013</span></span>](lync-server-2013-tls-and-mtls.md)

  - [<span data-ttu-id="4e2d6-121">Lync Server 2013 的加密</span><span class="sxs-lookup"><span data-stu-id="4e2d6-121">Encryption for Lync Server 2013</span></span>](lync-server-2013-encryption.md)

  - [<span data-ttu-id="4e2d6-122">Lync Server 2013 的使用者和用戶端驗證</span><span class="sxs-lookup"><span data-stu-id="4e2d6-122">User and client authentication for Lync Server 2013</span></span>](lync-server-2013-user-and-client-authentication.md)

  - [<span data-ttu-id="4e2d6-123">Windows PowerShell 和 Lync Server 2013 管理工具</span><span class="sxs-lookup"><span data-stu-id="4e2d6-123">Windows PowerShell and Lync Server 2013 management tools</span></span>](lync-server-2013-windows-powershell-and-lync-server-management-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

