---
title: Lync Server 2013：要求 edge 元件的憑證
description: Lync Server 2013：要求 edge 元件的憑證。
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
ms.openlocfilehash: 461e40921c88f26ce56141a8782ef2a04ce99667
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579009"
---
# <a name="request-certificates-for-edge-components-in-lync-server-2013"></a><span data-ttu-id="ad206-103">在 Lync Server 2013 中要求 edge 元件的憑證</span><span class="sxs-lookup"><span data-stu-id="ad206-103">Request certificates for edge components in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad206-104">_**主題上次修改日期：** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="ad206-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="ad206-105">支援外部使用者存取所需的憑證包括公用憑證授權單位 (CA) 所發出的憑證以及內部企業 CA 所發出的憑證：</span><span class="sxs-lookup"><span data-stu-id="ad206-105">The certificates required to support external user access include certificates issued by a public certification authority (CA), and certificates issued by an internal Enterprise CA:</span></span>

  - <span data-ttu-id="ad206-106">Edge Server 的外部介面及反向 proxy 所需的憑證必須由公用 CA 所發出。</span><span class="sxs-lookup"><span data-stu-id="ad206-106">Certificates required for the external interface of Edge Server and the reverse proxy must be issued by a public CA.</span></span>

  - <span data-ttu-id="ad206-107">內部介面所需的憑證可以由公用 CA 或內部企業 CA 所發出。</span><span class="sxs-lookup"><span data-stu-id="ad206-107">Certificates required for the internal interface can be issued by either a public CA or an internal enterprise CA.</span></span> <span data-ttu-id="ad206-108">我們建議使用內部 Windows Server 2008 CA、Windows Server 2008 R2 CA、Windows Server 2012 CA 或 Windows Server 2012 R2 CA，以建立這些憑證，以節約使用公用憑證的費用。</span><span class="sxs-lookup"><span data-stu-id="ad206-108">We recommend using an internal Windows Server 2008 CA, Windows Server 2008 R2 CA, Windows Server 2012 CA, or Windows Server 2012 R2 CA for creating these certificates to save on the expense of using public certificates.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ad206-109">處理憑證要求 (特別是公用 CA 的要求) 需要一些時間，因此應該及早要求 Edge Server 的憑證，以確保在您啟動 Edge Server 元件的部署時有憑證可用。</span><span class="sxs-lookup"><span data-stu-id="ad206-109">It can take time to process certificate requests, especially requests to public CAs, so you should request certificates for your Edge Servers early enough to ensure that they are available when you start deployment of your Edge Server components.</span></span> <span data-ttu-id="ad206-110">如需 Edge Server 之憑證需求的摘要，請參閱 <A href="lync-server-2013-certificate-requirements-for-external-user-access.md">Lync Server 2013 中外部使用者存取的憑證需求</A>。</span><span class="sxs-lookup"><span data-stu-id="ad206-110">For a summary of certificate requirements for Edge Servers, see <A href="lync-server-2013-certificate-requirements-for-external-user-access.md">Certificate requirements for external user access in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="ad206-111">雖然您可以選擇對內部 edge 憑證使用公用 CA，但建議您改用內部企業 CA 作為其他憑證，以將憑證成本降至最低。</span><span class="sxs-lookup"><span data-stu-id="ad206-111">Although you can choose to use a public CA for the internal edge certificate, we recommend that you use an internal enterprise CA for those other certificates instead to minimize the cost of certificates.</span></span> <span data-ttu-id="ad206-112">如需 Edge Server 之憑證需求的摘要，請參閱 [Lync Server 2013 中外部使用者存取的憑證需求](lync-server-2013-certificate-requirements-for-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="ad206-112">For a summary of certificate requirements for Edge Servers, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ad206-113">當您安裝 Edge Server 時，安裝程式會包含憑證嚮導，以協助要求、指派及安裝憑證的工作，如 <A href="lync-server-2013-set-up-edge-certificates.md">設定 Edge certificate For Lync Server 2013</A> 一節所述。</span><span class="sxs-lookup"><span data-stu-id="ad206-113">When you install an Edge Server, setup includes a certificate wizard that facilitates the tasks of requesting, assigning, and installing certificates, as described in the <A href="lync-server-2013-set-up-edge-certificates.md">Set up Edge certificates for Lync Server 2013</A> section.</span></span> <span data-ttu-id="ad206-114">如果您想要在安裝 Edge Server 之前要求憑證 (例如，在實際部署 Edge Server 元件時節省時間) ，只要您確定憑證是可匯出的，且包含所有必要的主體替代名稱，您就可以使用內部伺服器做到這一點。</span><span class="sxs-lookup"><span data-stu-id="ad206-114">If you want to request certificates prior to installing an Edge Server (such as to save time during actual deployment of Edge Server components), you can do so using internal servers as long as you ensure that the certificates are exportable and contain all of the required subject alternative names.</span></span> <span data-ttu-id="ad206-115">本檔不提供使用內部伺服器要求憑證的程式。</span><span class="sxs-lookup"><span data-stu-id="ad206-115">This documentation does not provide procedures for using internal servers to request certificates.</span></span>



</div>

<div>

## <a name="request-certificates-from-a-public-ca"></a><span data-ttu-id="ad206-116">從公用 CA 要求憑證</span><span class="sxs-lookup"><span data-stu-id="ad206-116">Request certificates from a public CA</span></span>

<span data-ttu-id="ad206-117">您的 Edge Server 部署需要一個公用憑證，以供 Edge Server 的外部介面使用，以供 Access Edge service、Web 會議 Edge service 和 A/V 驗證服務使用。</span><span class="sxs-lookup"><span data-stu-id="ad206-117">Your Edge Server deployment requires a single public certificate for the external interfaces of Edge Servers, which is used for the Access Edge service, the Web Conferencing Edge service, and for A/V authentication service.</span></span> <span data-ttu-id="ad206-118">此憑證必須具有可匯出的私密金鑰，以確保 A/V 驗證服務在集區中的所有 Edge Server 上都使用相同的機碼。</span><span class="sxs-lookup"><span data-stu-id="ad206-118">This certificate must have an exportable private key to ensure that the A/V authentication service uses the same keys on all Edge Servers in a pool.</span></span> <span data-ttu-id="ad206-119">與 Microsoft Internet Security and 加速 (ISA) Server 2006 或 Microsoft Forefront 威脅管理閘道2010搭配使用的反向 proxy，也需要公用憑證。</span><span class="sxs-lookup"><span data-stu-id="ad206-119">The reverse proxy, which is used with Microsoft Internet Security and Acceleration (ISA) Server 2006 or Microsoft Forefront Threat Management Gateway 2010, also requires a public certificate.</span></span>

</div>

<div>

## <a name="request-certificates-from-an-internal-enterprise-ca"></a><span data-ttu-id="ad206-120">從內部企業 CA 要求憑證</span><span class="sxs-lookup"><span data-stu-id="ad206-120">Request certificates from an internal Enterprise CA</span></span>

<span data-ttu-id="ad206-p106">內部邊緣介面所需的憑證，可由公用憑證授權單位 (CA) 或內部 CA 核發。使用內部企業 CA 有助於降低憑證成本。如果您的組織已部署內部 CA，內部邊緣的憑證即應由內部 CA 核發。以內部企業 CA 核發內部憑證，可降低憑證成本。</span><span class="sxs-lookup"><span data-stu-id="ad206-p106">The certificates required for the internal edge interface can be issued by either a public certification authority (CA) or an internal CA. You can use an internal enterprise CA to help minimize the cost of certificates. If your organization has an internal CA deployed, the certificates for the internal edge should be issued by the internal CA. Using an internal enterprise CA for internal certificates can reduce the cost of certificates.</span></span>

<span data-ttu-id="ad206-125">如需 edge 元件之憑證需求的摘要，請參閱 [Lync Server 2013 中外部使用者存取的憑證需求](lync-server-2013-certificate-requirements-for-external-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="ad206-125">For a summary of certificate requirements for edge components, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span> <span data-ttu-id="ad206-126">如需使用公用 CA 取得憑證的詳細資訊，請參閱 [在 Lync Server 2013 中要求 edge 元件的憑證](lync-server-2013-request-certificates-for-edge-components.md)。</span><span class="sxs-lookup"><span data-stu-id="ad206-126">For details about using a public CA to obtain certificates, see [Request certificates for edge components in Lync Server 2013](lync-server-2013-request-certificates-for-edge-components.md).</span></span> <span data-ttu-id="ad206-127">如需有關要求、安裝及指派憑證的詳細資訊，請參閱 [設定 Lync Server 2013 的 Edge 憑證](lync-server-2013-set-up-edge-certificates.md)。</span><span class="sxs-lookup"><span data-stu-id="ad206-127">For details about requesting, installing, and assigning certificates, see [Set up Edge certificates for Lync Server 2013](lync-server-2013-set-up-edge-certificates.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

