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
ms.openlocfilehash: 222cb12e38061c81a860092f90bf42d5412fdb63
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092281"
---
# <a name="microsoft-teams-for-realwear"></a><span data-ttu-id="8517e-103">Microsoft Teams for RealWear</span><span class="sxs-lookup"><span data-stu-id="8517e-103">Microsoft Teams for RealWear</span></span>

<span data-ttu-id="8517e-104">本文涵蓋適用於 RealWear 頭戴式穿戴裝置的 Microsoft Teams 用戶端。</span><span class="sxs-lookup"><span data-stu-id="8517e-104">This article covers the Microsoft Teams client for RealWear head-mounted wearables.</span></span> <span data-ttu-id="8517e-105">使用 RealWear HMT-1 和 HMT-1Z1 的第一線工作者現在可以使用 Teams 的視訊通話來與遠端專家共同作業。</span><span class="sxs-lookup"><span data-stu-id="8517e-105">Frontline Workers using RealWear HMT-1 and HMT-1Z1 can now collaborate with a remote expert using video calling on Teams.</span></span> <span data-ttu-id="8517e-106">透過語音控制的使用者介面，適用於 RealWear 的 Teams 允許現場工作者具有 100% 免持式能力，並且同時在吵雜與危險環境中保持對環境的警覺。</span><span class="sxs-lookup"><span data-stu-id="8517e-106">Through a voice-controlled user interface, Teams for RealWear allows field workers to remain 100% hands-free while maintaining situational awareness in loud and hazardous environments.</span></span> <span data-ttu-id="8517e-107">透過即時顯示現場工作者看到的內容，可協助現場工作者節省解決問題的時間，並降低昂貴的停機風險。</span><span class="sxs-lookup"><span data-stu-id="8517e-107">By showing what they see in real-time, field workers can accelerate the time to resolve issues and reduce the risk of an expensive downtime.</span></span>

## <a name="how-to-deploy-microsoft-teams-for-realwear"></a><span data-ttu-id="8517e-108">如何部署適用於 RealWear 的 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8517e-108">How to deploy Microsoft Teams for RealWear</span></span>

- <span data-ttu-id="8517e-109">RealWear 裝置更新為版本 11.2 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="8517e-109">RealWear devices updated to release 11.2 or above.</span></span> <span data-ttu-id="8517e-110">請在[這裡](https://realwear.com/knowledge-center/configure-on-release-10/wireless-update/) 取得更多資訊。</span><span class="sxs-lookup"><span data-stu-id="8517e-110">More information [here](https://realwear.com/knowledge-center/configure-on-release-10/wireless-update/).</span></span>
- <span data-ttu-id="8517e-111">存取 [RealWear Foresight](https://cloud.realwear.com/)，以發佈 Realwear 的Microsoft Teams 用戶端。</span><span class="sxs-lookup"><span data-stu-id="8517e-111">Access to [RealWear Foresight](https://cloud.realwear.com/) for distributing the Microsoft Teams client for Realwear.</span></span>

## <a name="required-licenses"></a><span data-ttu-id="8517e-112">所需授權</span><span class="sxs-lookup"><span data-stu-id="8517e-112">Required Licenses</span></span>

<span data-ttu-id="8517e-113">Microsoft Teams 授權屬於 Microsoft 365 和 Office 365 訂閱的一部分。</span><span class="sxs-lookup"><span data-stu-id="8517e-113">Microsoft Teams licenses are part of Microsoft 365 and Office 365 subscriptions.</span></span> <span data-ttu-id="8517e-114">使用適用於 RealWear 的 Teams 不需要額外的授權。</span><span class="sxs-lookup"><span data-stu-id="8517e-114">No additional licensing is required to use Teams for RealWear.</span></span> <span data-ttu-id="8517e-115">如需取得 Teams 的詳細資訊，請參閱 [如何取得 Microsoft Teams 存取權](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)。</span><span class="sxs-lookup"><span data-stu-id="8517e-115">For more information about getting Teams, check out [How do I get access to Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b).</span></span>

## <a name="managing-realwear-devices"></a><span data-ttu-id="8517e-116">管理 RealWear 裝置</span><span class="sxs-lookup"><span data-stu-id="8517e-116">Managing RealWear devices</span></span>

### <a name="microsoft-endpoint-manager"></a><span data-ttu-id="8517e-117">Microsoft 端點管理員</span><span class="sxs-lookup"><span data-stu-id="8517e-117">Microsoft Endpoint Manager</span></span>

<span data-ttu-id="8517e-118">您可以使用 Android 裝置系統管理員模式來管理 RealWear 裝置。</span><span class="sxs-lookup"><span data-stu-id="8517e-118">RealWear devices can be managed using Android Device Administrator mode.</span></span> <span data-ttu-id="8517e-119">由於裝置目前沒有提供 Google Mobile Services (GMS) ，因此透過 Android 企業版的管理支援有所限制。</span><span class="sxs-lookup"><span data-stu-id="8517e-119">Support for management via Android Enterprise is limited, as the devices currently don't have Google Mobile Services (GMS) available.</span></span>

- <span data-ttu-id="8517e-120">若要深入了解在 Microsoft 端點管理員上管理 RealWear 裝置的方法，請參閱 [Intune 中 Android 裝置系統管理員註冊](/mem/intune/enrollment/android-enroll-device-administrator)。</span><span class="sxs-lookup"><span data-stu-id="8517e-120">To learn more about managing RealWear devices on Microsoft Endpoint Manager, see [Android device administrator enrollment in Intune](/mem/intune/enrollment/android-enroll-device-administrator).</span></span>
- <span data-ttu-id="8517e-121">如需有關原則的詳細資訊，請參閱[如何在沒有 Google Mobile Services 的環境中使用 Intune](/mem/intune/apps/manage-without-gms)。</span><span class="sxs-lookup"><span data-stu-id="8517e-121">For more details on policies, see [How to use Intune in environments without Google Mobile Services](/mem/intune/apps/manage-without-gms).</span></span>

### <a name="third-party-enterprise-mobility-managers-emms"></a><span data-ttu-id="8517e-122">協力廠商企業行動力管理員 (EMM)</span><span class="sxs-lookup"><span data-stu-id="8517e-122">Third-party Enterprise Mobility Managers (EMMs)</span></span>

<span data-ttu-id="8517e-123">如需第三方 EMM 的指導方針，請參閱[支援的企業行動力管理提供者](https://www.realwear.com/knowledge-center/configure-on-release-10/remote-from-a-web-browser/emm/)。</span><span class="sxs-lookup"><span data-stu-id="8517e-123">For guidance on third-party EMMs, see [Supported Enterprise Mobility Management Providers](https://www.realwear.com/knowledge-center/configure-on-release-10/remote-from-a-web-browser/emm/).</span></span>

## <a name="end-user-content"></a><span data-ttu-id="8517e-124">使用者內容</span><span class="sxs-lookup"><span data-stu-id="8517e-124">End-user content</span></span>

<span data-ttu-id="8517e-125">若要從使用者觀點進一步了解，請參閱[使用 Microsoft Teams for RealWear](https://support.office.com/article/using-microsoft-teams-for-realwear-af20d232-d18c-476f-8031-843a4edccd5f)。</span><span class="sxs-lookup"><span data-stu-id="8517e-125">For further reading on this from an end-user perspective, please check out [Using Microsoft Teams for RealWear](https://support.office.com/article/using-microsoft-teams-for-realwear-af20d232-d18c-476f-8031-843a4edccd5f).</span></span>