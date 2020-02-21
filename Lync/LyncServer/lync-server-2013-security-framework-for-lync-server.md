---
title: 'Lync Server 2013: Lync server 的安全性架構'
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
ms.openlocfilehash: 7871d662d76f47685a58384804dfc6dee3b7b1d2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200909"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="security-framework-for-lync-server-2013"></a><span data-ttu-id="d4709-102">Lync Server 2013 的安全性架構</span><span class="sxs-lookup"><span data-stu-id="d4709-102">Security framework for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4709-103">_**上次修改主題：** 2013年-11-08_</span><span class="sxs-lookup"><span data-stu-id="d4709-103">_**Topic Last Modified:** 2013-11-08_</span></span>

<span data-ttu-id="d4709-104">本章節提供基本元素，讓表單 Microsoft Lync Server 2013 的安全性架構的概觀。</span><span class="sxs-lookup"><span data-stu-id="d4709-104">This section provides an overview of the fundamental elements that form the security framework for Microsoft Lync Server 2013.</span></span> <span data-ttu-id="d4709-105">了解這些項目共同運作的方式是不可或缺的相關保護您特定的 Lync Server 2013 部署明智決策。</span><span class="sxs-lookup"><span data-stu-id="d4709-105">Understanding how these elements work together is essential to making informed decisions about securing your particular Lync Server 2013 deployment.</span></span>

<span data-ttu-id="d4709-106">這些元素如下所示：</span><span class="sxs-lookup"><span data-stu-id="d4709-106">These elements are as follows:</span></span>

  - <span data-ttu-id="d4709-107">Active Directory 網域服務 (AD DS) 提供單一受信任的後端儲存機制的使用者帳戶及網路資源。</span><span class="sxs-lookup"><span data-stu-id="d4709-107">Active Directory Domain Services (AD DS) provides a single trusted back-end repository for user accounts and network resources.</span></span>

  - <span data-ttu-id="d4709-108">角色型存取控制 (RBAC) 可讓您管理工作委派維持高標準的安全性。</span><span class="sxs-lookup"><span data-stu-id="d4709-108">Role-Based Access Control (RBAC) enables you to delegate administrative tasks while maintaining high standards for security.</span></span>

  - <span data-ttu-id="d4709-109">公開金鑰基礎結構 (PKI) 使用受信任的憑證授權單位 (Ca) 所發出的憑證來驗證伺服器，並確保資料完整性。</span><span class="sxs-lookup"><span data-stu-id="d4709-109">Public Key Infrastructure (PKI) uses certificates issued by trusted certification authorities (CAs) to authenticate servers and ensure data integrity.</span></span>

  - <span data-ttu-id="d4709-110">傳輸層安全性 (TLS) HTTPS over SSL (HTTPS) 和相互 TLS (MTLS) 啟用端點驗證及 IM 加密。</span><span class="sxs-lookup"><span data-stu-id="d4709-110">Transport Layer Security (TLS), HTTPS over SSL (HTTPS), and mutual TLS (MTLS) enable endpoint authentication and IM encryption.</span></span> <span data-ttu-id="d4709-111">使用安全即時傳輸通訊協定 (SRTP) 會加密點對點音訊、 視訊及應用程式共用資料流。</span><span class="sxs-lookup"><span data-stu-id="d4709-111">Point-to-point audio, video, and application sharing streams are encrypted using Secure Real-Time Transport Protocol (SRTP).</span></span>

  - <span data-ttu-id="d4709-112">請儘可能進行使用者驗證通訊協定業界標準。</span><span class="sxs-lookup"><span data-stu-id="d4709-112">Industry-standard protocols for user authentication, where possible.</span></span>

  - <span data-ttu-id="d4709-113">Windows PowerShell 提供的安全性功能，讓使用者無法輕易地或不知情的情況下執行指令碼，依預設而啟用。</span><span class="sxs-lookup"><span data-stu-id="d4709-113">Windows PowerShell provides security features that are enabled by default so that users cannot easily or unknowingly run scripts.</span></span>

<span data-ttu-id="d4709-114">這些基本安全性要素會共同運作來定義信任的使用者、 伺服器、 連線以及作業，以協助確保 Lync Server 2013 的安全基礎。</span><span class="sxs-lookup"><span data-stu-id="d4709-114">These fundamental security elements work together to define trusted users, servers, connections, and operations to help ensure a secure foundation for Lync Server 2013.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d4709-115">本章節內容</span><span class="sxs-lookup"><span data-stu-id="d4709-115">In This Section</span></span>

<span data-ttu-id="d4709-116">本節中的主題會說明每個這些基礎元素增強安全性，Lync Server 基礎結構的運作方式。</span><span class="sxs-lookup"><span data-stu-id="d4709-116">The topics in this section describe how each of these fundamental elements works to enhance the security of your Lync Server infrastructure.</span></span>

  - [<span data-ttu-id="d4709-117">Lync Server 2013 的 active Directory 網域服務</span><span class="sxs-lookup"><span data-stu-id="d4709-117">Active Directory Domain Services for Lync Server 2013</span></span>](lync-server-2013-active-directory-domain-services-for-lync-server.md)

  - [<span data-ttu-id="d4709-118">Lync Server 2013 的角色型存取控制 (RBAC)</span><span class="sxs-lookup"><span data-stu-id="d4709-118">Role-based access control (RBAC) for Lync Server 2013</span></span>](lync-server-2013-role-based-access-control-rbac.md)

  - [<span data-ttu-id="d4709-119">Lync Server 2013 的公開金鑰基礎結構</span><span class="sxs-lookup"><span data-stu-id="d4709-119">Public Key Infrastructure for Lync Server 2013</span></span>](lync-server-2013-public-key-infrastructure.md)

  - [<span data-ttu-id="d4709-120">Lync Server 2013 的 TLS 和 MTLS</span><span class="sxs-lookup"><span data-stu-id="d4709-120">TLS and MTLS for Lync Server 2013</span></span>](lync-server-2013-tls-and-mtls.md)

  - [<span data-ttu-id="d4709-121">Lync Server 2013 的加密</span><span class="sxs-lookup"><span data-stu-id="d4709-121">Encryption for Lync Server 2013</span></span>](lync-server-2013-encryption.md)

  - [<span data-ttu-id="d4709-122">Lync Server 2013 的使用者與用戶端驗證</span><span class="sxs-lookup"><span data-stu-id="d4709-122">User and client authentication for Lync Server 2013</span></span>](lync-server-2013-user-and-client-authentication.md)

  - [<span data-ttu-id="d4709-123">Windows PowerShell 和 Lync Server 2013 管理工具</span><span class="sxs-lookup"><span data-stu-id="d4709-123">Windows PowerShell and Lync Server 2013 management tools</span></span>](lync-server-2013-windows-powershell-and-lync-server-management-tools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

