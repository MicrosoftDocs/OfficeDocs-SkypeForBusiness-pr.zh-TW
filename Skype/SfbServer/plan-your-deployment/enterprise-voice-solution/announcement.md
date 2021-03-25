---
title: 在商務用 Skype 中規劃宣告應用程式
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2abee804-2599-48bb-90b2-15df0bae5e20
description: 在商務用 Skype Server Enterprise Voice 中規劃宣告應用程式，以設定組織中未指派電話號碼的電話通話方式。 包括音訊檔需求。
ms.openlocfilehash: e1309fe58942f3b9cd720b3643966ae9494bb0cb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51112709"
---
# <a name="plan-for-the-announcement-application-in-skype-for-business"></a><span data-ttu-id="789c8-104">在商務用 Skype 中規劃宣告應用程式</span><span class="sxs-lookup"><span data-stu-id="789c8-104">Plan for the Announcement application in Skype for Business</span></span>

<span data-ttu-id="789c8-105">在商務用 Skype Server Enterprise Voice 中規劃宣告應用程式，以設定組織中未指派電話號碼的電話通話方式。</span><span class="sxs-lookup"><span data-stu-id="789c8-105">Planning for the announcement application in Skype for Business Server Enterprise Voice, which configures what to do with phone calls to unassigned phone numbers in your organizations.</span></span> <span data-ttu-id="789c8-106">包括音訊檔需求。</span><span class="sxs-lookup"><span data-stu-id="789c8-106">Includes audio file requirements.</span></span>

<span data-ttu-id="789c8-107">商務用 Skype 伺服器宣告應用程式可讓您設定撥打的電話號碼對您的組織有效，但未指派給使用者或電話的來電處理。</span><span class="sxs-lookup"><span data-stu-id="789c8-107">The Skype for Business Server Announcement application enables you to configure the handling of incoming phone calls when the dialed number is valid for your organization, but is not assigned to a user or a phone.</span></span> <span data-ttu-id="789c8-108">您可以將這些通話轉接至預先定義的目的地 (電話號碼、SIP URI 或語音信箱) 或播放音訊宣告或兩者。</span><span class="sxs-lookup"><span data-stu-id="789c8-108">You can transfer these calls to a predetermined destination (phone number, SIP URI, or voice mail), or play an audio announcement, or both.</span></span> <span data-ttu-id="789c8-109">宣告應用程式可協助您避免來電者 misdials 並聽到忙碌色調或 SIP 用戶端收到錯誤訊息的情況。</span><span class="sxs-lookup"><span data-stu-id="789c8-109">The Announcement application helps you avoid the situations in which a caller misdials and hears a busy tone or the SIP client receives an error message.</span></span> <span data-ttu-id="789c8-110">本節包含宣告應用程式特有的規劃資訊</span><span class="sxs-lookup"><span data-stu-id="789c8-110">This section includes planning information that is specific to the Announcement application</span></span>

<span data-ttu-id="789c8-111">當您部署宣告應用程式時，您必須設定未指派的號碼表，以決定當某人撥打未指派的號碼時要採取的動作。</span><span class="sxs-lookup"><span data-stu-id="789c8-111">When you deploy the Announcement application, you need to configure an unassigned number table that determines the action to be taken when someone dials an unassigned number.</span></span> <span data-ttu-id="789c8-112">「未指派的號碼」表包含對組織有效的電話號碼範圍，並指定哪個宣告應用程式會處理每個範圍。</span><span class="sxs-lookup"><span data-stu-id="789c8-112">The unassigned number table contains ranges of phone numbers that are valid for the organization and specifies which Announcement application handles each range.</span></span> <span data-ttu-id="789c8-113">當來電者撥打對您的組織有效的電話號碼，但未指派給任何人時，商務用 Skype Server 會查詢未指派號碼路由表中的號碼，識別該號碼屬於哪個範圍，並將通話路由傳送至該範圍所指定的宣告應用程式。</span><span class="sxs-lookup"><span data-stu-id="789c8-113">When a caller dials a telephone number that is valid for your organization but is not assigned to anyone, Skype for Business Server looks up the number in the unassigned number routing table, identifies which range the number falls in, and routes the call to the Announcement application specified for that range.</span></span> <span data-ttu-id="789c8-114">宣告應用程式會接聽來電，並 (如果將其設定為執行這項操作，則) 然後中斷通話，或將其轉接至預先決定的目的地，例如操作員。</span><span class="sxs-lookup"><span data-stu-id="789c8-114">The Announcement application answers the call and plays an audio message (if you configured it to do so) and then either disconnects the call or transfers it to a predetermined destination, such as to an operator.</span></span> <span data-ttu-id="789c8-115">您可以使用商務用 Skype Server 管理命令介面 Cmdlet 來設定多個音訊訊息，或傳送目的地。</span><span class="sxs-lookup"><span data-stu-id="789c8-115">You can use Skype for Business Server Management Shell cmdlets to configure multiple audio messages or to transfer destinations.</span></span>

<span data-ttu-id="789c8-p105">設定未指派號碼表的方式取決於其使用方式。如果您有不再使用的特定號碼，而且想要播放專為各個號碼而設計的訊息，則可以在未指派號碼表中輸入那些特定號碼。例如，如果您變更了客戶服務中心的號碼，則可以輸入舊的客戶服務號碼，並將其與宣告相關聯，以提供新號碼。如果您想要對撥打未指派之號碼的任何人 (如離職員工) 播放一般訊息，則可以輸入您組織中所有有效分機的範圍。只要來電者撥打目前未指派的號碼，就會叫用未指派號碼表。</span><span class="sxs-lookup"><span data-stu-id="789c8-p105">How you configure the unassigned number table depends on how you want to use it. If you have specific numbers that are no longer in use and you want to play messages that are tailored for each number, you can enter those specific numbers in the unassigned number table. For example, if you changed the number for your customer service desk, you can enter the old customer service number and associate it with an announcement that gives the new number. If you want to play a general message to anyone who calls a number that is not assigned, such as for employees who have left your organization, you can enter ranges for all the valid extensions in your organization. The unassigned number table is invoked whenever the caller dials a number that is not currently assigned.</span></span>

## <a name="deployment-and-requirements"></a><span data-ttu-id="789c8-121">部署和需求</span><span class="sxs-lookup"><span data-stu-id="789c8-121">Deployment and requirements</span></span>

<span data-ttu-id="789c8-122">宣告應用程式會自動隨回應群組應用程式一起安裝。</span><span class="sxs-lookup"><span data-stu-id="789c8-122">Tthe Announcement application is automatically installed with the Response Group application.</span></span> <span data-ttu-id="789c8-123">宣告及回應群組應用程式是企業語音部署的標準元件：當您部署企業語音時，會自動部署這兩個應用程式。</span><span class="sxs-lookup"><span data-stu-id="789c8-123">The Announcement and Response Group applications are standard components of an Enterprise Voice deployment: When you deploy Enterprise Voice, both of these applications are automatically deployed.</span></span>

### <a name="software-requirements"></a><span data-ttu-id="789c8-124">軟體需求</span><span class="sxs-lookup"><span data-stu-id="789c8-124">Software requirements</span></span>

<span data-ttu-id="789c8-125">執行宣告應用程式的所有前端伺服器或 Standard Edition 伺服器，都必須為執行 windows Server 2008 R2 的伺服器安裝 Windows Media Format Runtime，或為執行 Windows Server 2012 或 Windows Server 2012 R2 的伺服器安裝 Microsoft Media Foundation。</span><span class="sxs-lookup"><span data-stu-id="789c8-125">All Front End Servers or Standard Edition servers that run the Announcement application must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="789c8-126">若為 Windows Server 2008 R2，Windows Media Format Runtime 會安裝為 Windows 桌面體驗的一部分。</span><span class="sxs-lookup"><span data-stu-id="789c8-126">For Windows Server 2008 R2, the Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span> <span data-ttu-id="789c8-127">Windows media Audio ( 的 windows media Format Runtime 或 Microsoft Media Foundation 是 Windows Media Audio 的必要功能。宣告應用程式針對宣告和音樂所播放的 wma) 檔案。</span><span class="sxs-lookup"><span data-stu-id="789c8-127">Windows Media Format Runtime or Microsoft Media Foundation is required for Windows Media Audio (.wma) files that the Announcement application plays for announcements and music.</span></span>

### <a name="port-requirements"></a><span data-ttu-id="789c8-128">連接埠需求</span><span class="sxs-lookup"><span data-stu-id="789c8-128">Port Requirements</span></span>

<span data-ttu-id="789c8-129">宣告應用程式會使用 **埠 5071** 進行 SIP 聆聽要求。</span><span class="sxs-lookup"><span data-stu-id="789c8-129">The Announcement application uses **Port 5071** for SIP listening requests.</span></span>

> [!NOTE]
> <span data-ttu-id="789c8-130">此埠是預設設定，您可以使用 **Set-CsApplicationServer** Cmdlet 進行變更。</span><span class="sxs-lookup"><span data-stu-id="789c8-130">This port is the default setting, which you can change by using the **Set-CsApplicationServer** cmdlet.</span></span> <span data-ttu-id="789c8-131">如需此 Cmdlet 的詳細資訊，請參閱商務用 Skype Server 管理命令介面檔。</span><span class="sxs-lookup"><span data-stu-id="789c8-131">For details about this cmdlet, see the Skype for Business Server Management Shell documentation.</span></span>

### <a name="audio-file-requirements"></a><span data-ttu-id="789c8-132">音訊檔案需求</span><span class="sxs-lookup"><span data-stu-id="789c8-132">Audio File Requirements</span></span>

<span data-ttu-id="789c8-133">宣告應用程式支援波形 ( .wav) 檔案格式和 Windows Media 音訊)  ( 的音樂和宣告的檔案格式。</span><span class="sxs-lookup"><span data-stu-id="789c8-133">The Announcement application supports Wave (.wav) file format and Windows Media audio (.wma) file format for music and announcements.</span></span> <span data-ttu-id="789c8-134">宣告應用程式的音訊檔需求與回應群組應用程式相同。</span><span class="sxs-lookup"><span data-stu-id="789c8-134">Audio file requirements for the Announcement application are the same as for the Response Group application.</span></span> <span data-ttu-id="789c8-135">如需詳細資訊，請參閱 [回應群組的技術需求](/previous-versions/office/lync-server-2013/lync-server-2013-technical-requirements-for-response-group)。</span><span class="sxs-lookup"><span data-stu-id="789c8-135">For details, see [Technical Requirements for Response Groups](/previous-versions/office/lync-server-2013/lync-server-2013-technical-requirements-for-response-group).</span></span>