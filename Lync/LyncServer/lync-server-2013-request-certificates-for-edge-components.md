---
title: Lync Server 2013：要求 Edge 元件的憑證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Request certificates for edge components
ms:assetid: 8c72b877-febc-428f-89dc-389e7a7ac849
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398708(v=OCS.15)
ms:contentKeyID: 48184779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 096603b48e6a3636a397c4abf7c19c2b4237f132
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763315"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="request-certificates-for-edge-components-in-lync-server-2013"></a><span data-ttu-id="677f6-102">在 Lync Server 2013 中要求 Edge 元件的憑證</span><span class="sxs-lookup"><span data-stu-id="677f6-102">Request certificates for edge components in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="677f6-103">_**主題上次修改日期：** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="677f6-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="677f6-104">支援外部使用者存取所需的憑證包括由公用憑證授權單位（CA）所頒發的憑證，以及由內部企業 CA 所頒發的憑證：</span><span class="sxs-lookup"><span data-stu-id="677f6-104">The certificates required to support external user access include certificates issued by a public certification authority (CA), and certificates issued by an internal Enterprise CA:</span></span>

  - <span data-ttu-id="677f6-105">Edge 伺服器外部介面所需的憑證和反向 proxy 必須由公用 CA 所頒發。</span><span class="sxs-lookup"><span data-stu-id="677f6-105">Certificates required for the external interface of Edge Server and the reverse proxy must be issued by a public CA.</span></span>

  - <span data-ttu-id="677f6-106">內部介面所需的憑證可以由公用 CA 或內部企業 CA 發出。</span><span class="sxs-lookup"><span data-stu-id="677f6-106">Certificates required for the internal interface can be issued by either a public CA or an internal enterprise CA.</span></span> <span data-ttu-id="677f6-107">我們建議您使用內部 Windows Server 2008 CA、Windows Server 2008 R2 CA、Windows Server 2012 CA，或 Windows server 2012 R2 CA 來建立這些憑證，以使用公用憑證的費用來儲存。</span><span class="sxs-lookup"><span data-stu-id="677f6-107">We recommend using an internal Windows Server 2008 CA, Windows Server 2008 R2 CA, Windows Server 2012 CA, or Windows Server 2012 R2 CA for creating these certificates to save on the expense of using public certificates.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="677f6-108">處理證書要求的時間可能需要一些時間，特別是公用 Ca 的要求，因此您應該提前為邊緣伺服器要求證書，以確保您開始部署 Edge 伺服器元件時可以使用它們。</span><span class="sxs-lookup"><span data-stu-id="677f6-108">It can take time to process certificate requests, especially requests to public CAs, so you should request certificates for your Edge Servers early enough to ensure that they are available when you start deployment of your Edge Server components.</span></span> <span data-ttu-id="677f6-109">如需邊緣伺服器的憑證需求摘要，請參閱<A href="lync-server-2013-certificate-requirements-for-external-user-access.md">Lync Server 2013 中的外部使用者存取證書需求</A>。</span><span class="sxs-lookup"><span data-stu-id="677f6-109">For a summary of certificate requirements for Edge Servers, see <A href="lync-server-2013-certificate-requirements-for-external-user-access.md">Certificate requirements for external user access in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="677f6-110">雖然您可以選擇將公用 CA 用於內部邊緣證書，但我們建議您將內部企業 CA 用於其他證書，而不是將憑證的成本降至最低。</span><span class="sxs-lookup"><span data-stu-id="677f6-110">Although you can choose to use a public CA for the internal edge certificate, we recommend that you use an internal enterprise CA for those other certificates instead to minimize the cost of certificates.</span></span> <span data-ttu-id="677f6-111">如需邊緣伺服器的憑證需求摘要，請參閱[Lync Server 2013 中的外部使用者存取證書需求](lync-server-2013-certificate-requirements-for-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="677f6-111">For a summary of certificate requirements for Edge Servers, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="677f6-112">當您安裝 Edge 伺服器時，安裝程式會包含可協助要求、指派及安裝憑證之工作的憑證嚮導，如 [<A href="lync-server-2013-set-up-edge-certificates.md">設定 Lync Server 2013 的邊緣憑證</A>] 區段中所述。</span><span class="sxs-lookup"><span data-stu-id="677f6-112">When you install an Edge Server, setup includes a certificate wizard that facilitates the tasks of requesting, assigning, and installing certificates, as described in the <A href="lync-server-2013-set-up-edge-certificates.md">Set up Edge certificates for Lync Server 2013</A> section.</span></span> <span data-ttu-id="677f6-113">如果您想要在安裝邊緣伺服器之前（例如在邊緣伺服器元件的實際部署期間節省時間），您可以使用內部伺服器來執行此操作，只要確保憑證可匯出且包含所有必要的消費者替換名稱。</span><span class="sxs-lookup"><span data-stu-id="677f6-113">If you want to request certificates prior to installing an Edge Server (such as to save time during actual deployment of Edge Server components), you can do so using internal servers as long as you ensure that the certificates are exportable and contain all of the required subject alternative names.</span></span> <span data-ttu-id="677f6-114">本檔不提供使用內部伺服器來申請憑證的程式。</span><span class="sxs-lookup"><span data-stu-id="677f6-114">This documentation does not provide procedures for using internal servers to request certificates.</span></span>



</div>

<div>

## <a name="request-certificates-from-a-public-ca"></a><span data-ttu-id="677f6-115">從公用 CA 申請憑證</span><span class="sxs-lookup"><span data-stu-id="677f6-115">Request certificates from a public CA</span></span>

<span data-ttu-id="677f6-116">Edge 伺服器部署需要一個適用于 Edge 伺服器外部介面的公用憑證，用於存取邊緣服務、網路會議 Edge 服務，以及 A/V 驗證服務。</span><span class="sxs-lookup"><span data-stu-id="677f6-116">Your Edge Server deployment requires a single public certificate for the external interfaces of Edge Servers, which is used for the Access Edge service, the Web Conferencing Edge service, and for A/V authentication service.</span></span> <span data-ttu-id="677f6-117">這個憑證必須有可匯出的私密金鑰，以確保 A/V 驗證服務在池中的所有邊緣伺服器上都使用相同的金鑰。</span><span class="sxs-lookup"><span data-stu-id="677f6-117">This certificate must have an exportable private key to ensure that the A/V authentication service uses the same keys on all Edge Servers in a pool.</span></span> <span data-ttu-id="677f6-118">與 Microsoft Internet Security 和加速度（ISA） Server 2006 或 Microsoft Forefront 威脅管理閘道2010搭配使用的反向 proxy，也需要公用憑證。</span><span class="sxs-lookup"><span data-stu-id="677f6-118">The reverse proxy, which is used with Microsoft Internet Security and Acceleration (ISA) Server 2006 or Microsoft Forefront Threat Management Gateway 2010, also requires a public certificate.</span></span>

</div>

<div>

## <a name="request-certificates-from-an-internal-enterprise-ca"></a><span data-ttu-id="677f6-119">從內部企業 CA 申請憑證</span><span class="sxs-lookup"><span data-stu-id="677f6-119">Request certificates from an internal Enterprise CA</span></span>

<span data-ttu-id="677f6-120">內部邊緣介面所需的憑證可以由公用憑證授權單位（CA）或內部 CA 發出。</span><span class="sxs-lookup"><span data-stu-id="677f6-120">The certificates required for the internal edge interface can be issued by either a public certification authority (CA) or an internal CA.</span></span> <span data-ttu-id="677f6-121">您可以使用內部企業 CA，協助將憑證的成本降至最低。</span><span class="sxs-lookup"><span data-stu-id="677f6-121">You can use an internal enterprise CA to help minimize the cost of certificates.</span></span> <span data-ttu-id="677f6-122">如果您的組織已部署內部 CA，內部邊緣的憑證應該由內部 CA 頒發。</span><span class="sxs-lookup"><span data-stu-id="677f6-122">If your organization has an internal CA deployed, the certificates for the internal edge should be issued by the internal CA.</span></span> <span data-ttu-id="677f6-123">使用內部憑證的內部企業 CA 可減少憑證的成本。</span><span class="sxs-lookup"><span data-stu-id="677f6-123">Using an internal enterprise CA for internal certificates can reduce the cost of certificates.</span></span>

<span data-ttu-id="677f6-124">如需邊緣元件的憑證需求摘要，請參閱[Lync Server 2013 中的外部使用者存取證書需求](lync-server-2013-certificate-requirements-for-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="677f6-124">For a summary of certificate requirements for edge components, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span> <span data-ttu-id="677f6-125">如需使用公用 CA 取得憑證的詳細資料，請參閱[在 Lync Server 2013 中針對 edge 元件申請證書](lync-server-2013-request-certificates-for-edge-components.md)。</span><span class="sxs-lookup"><span data-stu-id="677f6-125">For details about using a public CA to obtain certificates, see [Request certificates for edge components in Lync Server 2013](lync-server-2013-request-certificates-for-edge-components.md).</span></span> <span data-ttu-id="677f6-126">如需有關要求、安裝及指派證書的詳細資料，請參閱[設定 Lync Server 2013 的邊緣憑證](lync-server-2013-set-up-edge-certificates.md)。</span><span class="sxs-lookup"><span data-stu-id="677f6-126">For details about requesting, installing, and assigning certificates, see [Set up Edge certificates for Lync Server 2013](lync-server-2013-set-up-edge-certificates.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

