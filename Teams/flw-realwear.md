---
title: 適用於 Microsoft Teams for RealWear 用戶端的 ITAdmin 資訊 (預覽)
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: 適用於 Microsoft Teams for RealWear 用戶端的 ITAdmin 逐步解說。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: e95440652111dbcd39b756ef942e7a974ef31de0
ms.sourcegitcommit: dc6108917392754d950cea47b92f871211bf4212
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/03/2020
ms.locfileid: "43131201"
---
# <a name="microsoft-teams-for-realwear"></a><span data-ttu-id="b3b1a-103">Microsoft Teams for RealWear</span><span class="sxs-lookup"><span data-stu-id="b3b1a-103">Microsoft Teams for RealWear</span></span>

> [!NOTE]
> <span data-ttu-id="b3b1a-104">這是預覽或早期版本功能。</span><span class="sxs-lookup"><span data-stu-id="b3b1a-104">This is a preview or early release feature.</span></span>

<span data-ttu-id="b3b1a-105">本文涵蓋適用於 RealWear 頭戴式穿戴裝置的 Microsoft Teams 用戶端。</span><span class="sxs-lookup"><span data-stu-id="b3b1a-105">This article covers the Microsoft Teams client for RealWear head-mounted wearables.</span></span> <span data-ttu-id="b3b1a-106">使用 RealWear HMT-1 和 HMT-1Z1 的第一線工作者現在可以使用 Teams 的視訊通話來與遠端專業人員共同作業。</span><span class="sxs-lookup"><span data-stu-id="b3b1a-106">FirstLine Workers using RealWear HMT-1 and HMT-1Z1 can now collaborate with a remote expert using video calling on Teams.</span></span> <span data-ttu-id="b3b1a-107">透過語音控制的使用者介面，適用於 RealWear 的 Teams 允許現場工作者具有 100% 免持式能力，並且同時在吵雜與危險環境中保持對環境的警覺。</span><span class="sxs-lookup"><span data-stu-id="b3b1a-107">Through a voice-controlled user interface, Teams for RealWear allows field workers to remain 100% hands-free while maintaining situational awareness in loud and hazardous environments.</span></span> <span data-ttu-id="b3b1a-108">透過即時顯示現場工作者看到的內容，可協助現場工作者節省解決問題的時間，並降低昂貴的停機風險。</span><span class="sxs-lookup"><span data-stu-id="b3b1a-108">By showing what they see in real-time, field workers can accelerate the time to resolve issues and reduce the risk of an expensive downtime.</span></span>

## <a name="how-to-deploy-microsoft-teams-for-realwear"></a><span data-ttu-id="b3b1a-109">如何部署適用於 RealWear 的 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b3b1a-109">How to deploy Microsoft Teams for RealWear</span></span>

<span data-ttu-id="b3b1a-110">適用於 RealWear 的 Microsoft Teams 用戶端目前為公開預覽。</span><span class="sxs-lookup"><span data-stu-id="b3b1a-110">Microsoft Teams client for RealWear is currently in Public Preview.</span></span> <span data-ttu-id="b3b1a-111">若要參與此預覽，您需要具備以下項目：</span><span class="sxs-lookup"><span data-stu-id="b3b1a-111">To participate in this preview, you will need the following:</span></span>

<span data-ttu-id="b3b1a-112">RealWear 裝置更新為版本10.5.0 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="b3b1a-112">RealWear devices updated to release 10.5.0 or above.</span></span> <span data-ttu-id="b3b1a-113">請在[這裡](https://realwear.com/knowledge-center/configure-on-release-10/wireless-update/) 取得更多資訊。</span><span class="sxs-lookup"><span data-stu-id="b3b1a-113">More information [here](https://realwear.com/knowledge-center/configure-on-release-10/wireless-update/).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b3b1a-114">請在 [這裡](https://www.realwear.com/solutions/microsoft-teams/#C1)註冊以存取 [RealWear 展望](https://cloud.realwear.com/) (英文) 中之適用於 RealWear 用戶端的 Teams。</span><span class="sxs-lookup"><span data-stu-id="b3b1a-114">Register [here](https://www.realwear.com/solutions/microsoft-teams/#C1) for access to Teams for RealWear client in [RealWear Foresight](https://cloud.realwear.com/).</span></span>

## <a name="required-licenses"></a><span data-ttu-id="b3b1a-115">所需授權</span><span class="sxs-lookup"><span data-stu-id="b3b1a-115">Required Licenses</span></span>

<span data-ttu-id="b3b1a-116">Microsoft Teams 授權屬於 Office 365 訂閱的一部分。</span><span class="sxs-lookup"><span data-stu-id="b3b1a-116">Microsoft Teams licenses are part of Office 365 subscriptions.</span></span> <span data-ttu-id="b3b1a-117">使用適用於 RealWear 的 Teams 不需要額外的授權。</span><span class="sxs-lookup"><span data-stu-id="b3b1a-117">No additional licensing is required to use Teams for RealWear.</span></span> <span data-ttu-id="b3b1a-118">如需取得 Teams 的詳細資訊，請參閱 [如何取得 Microsoft Teams 存取權](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)。</span><span class="sxs-lookup"><span data-stu-id="b3b1a-118">For more information about getting Teams, check out [How do I get access to Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b).</span></span>

## <a name="managing-realwear-devices"></a><span data-ttu-id="b3b1a-119">管理 RealWear 裝置</span><span class="sxs-lookup"><span data-stu-id="b3b1a-119">Managing RealWear devices</span></span>

### <a name="microsoft-endpoint-manager"></a><span data-ttu-id="b3b1a-120">Microsoft 端點管理員</span><span class="sxs-lookup"><span data-stu-id="b3b1a-120">Microsoft Endpoint Manager</span></span>

<span data-ttu-id="b3b1a-121">您可以使用 Android 裝置系統管理員模式來管理 RealWear 裝置。</span><span class="sxs-lookup"><span data-stu-id="b3b1a-121">RealWear devices can be managed using Android Device Administrator mode.</span></span> <span data-ttu-id="b3b1a-122">由於裝置目前沒有提供 Google Mobile Services (GMS) ，因此透過 Android 企業版的管理支援有所限制。</span><span class="sxs-lookup"><span data-stu-id="b3b1a-122">Support for management via Android Enterprise is limited, as the devices currently don't have Google Mobile Services (GMS) available.</span></span>

- <span data-ttu-id="b3b1a-123">若要深入了解在 Microsoft 端點管理員上管理 RealWear 裝置的方法，請參閱 [Intune 中 Android 裝置系統管理員註冊](https://docs.microsoft.com/mem/intune/enrollment/android-enroll-device-administrator) (英文)。</span><span class="sxs-lookup"><span data-stu-id="b3b1a-123">To learn more about managing RealWear devices on Microsoft Endpoint Manager, see [Android device administrator enrollment in Intune](https://docs.microsoft.com/mem/intune/enrollment/android-enroll-device-administrator).</span></span>
- <span data-ttu-id="b3b1a-124">如需有關原則的詳細資訊，請參閱[如何在沒有 Google Mobile Services 的環境中使用 Intune](https://docs.microsoft.com/mem/intune/apps/manage-without-gms) (英文)。</span><span class="sxs-lookup"><span data-stu-id="b3b1a-124">For more details on policies, see [How to use Intune in environments without Google Mobile Services](https://docs.microsoft.com/mem/intune/apps/manage-without-gms).</span></span>

### <a name="third-party-enterprise-mobility-managers-emms"></a><span data-ttu-id="b3b1a-125">協力廠商企業行動力管理員 (EMM)</span><span class="sxs-lookup"><span data-stu-id="b3b1a-125">Third-party Enterprise Mobility Managers (EMMs)</span></span>

<span data-ttu-id="b3b1a-126">如需第三方 EMM 的指導方針，請參閱[支援的企業行動力管理提供者](https://www.realwear.com/knowledge-center/configure-on-release-10/remote-from-a-web-browser/emm/) (英文)。</span><span class="sxs-lookup"><span data-stu-id="b3b1a-126">For guidance on third-party EMMs, see [Supported Enterprise Mobility Management Providers](https://www.realwear.com/knowledge-center/configure-on-release-10/remote-from-a-web-browser/emm/).</span></span>

## <a name="end-user-content"></a><span data-ttu-id="b3b1a-127">使用者內容</span><span class="sxs-lookup"><span data-stu-id="b3b1a-127">End-user content</span></span>

<span data-ttu-id="b3b1a-128">若要從使用者觀點進一步了解，請參閱[使用 Microsoft Teams for RealWear](https://support.office.com/article/using-microsoft-teams-for-realwear-af20d232-d18c-476f-8031-843a4edccd5f)。</span><span class="sxs-lookup"><span data-stu-id="b3b1a-128">For further reading on this from an end-user perspective, please check out [Using Microsoft Teams for RealWear](https://support.office.com/article/using-microsoft-teams-for-realwear-af20d232-d18c-476f-8031-843a4edccd5f).</span></span>
