---
title: 規劃商務用 Skype 中的宣告應用程式
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2abee804-2599-48bb-90b2-15df0bae5e20
description: 規劃商務用 Skype Server Enterprise Voice 中的宣告應用程式，在您的組織中設定電話撥出未指派電話號碼的方式。 包括音訊檔需求。
ms.openlocfilehash: d160878030fad30dd3e91b78f54ffcdab722299f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803263"
---
# <a name="plan-for-the-announcement-application-in-skype-for-business"></a><span data-ttu-id="2bbb7-104">規劃商務用 Skype 中的宣告應用程式</span><span class="sxs-lookup"><span data-stu-id="2bbb7-104">Plan for the Announcement application in Skype for Business</span></span>

<span data-ttu-id="2bbb7-105">規劃商務用 Skype Server Enterprise Voice 中的宣告應用程式，在您的組織中設定電話撥出未指派電話號碼的方式。</span><span class="sxs-lookup"><span data-stu-id="2bbb7-105">Planning for the announcement application in Skype for Business Server Enterprise Voice, which configures what to do with phone calls to unassigned phone numbers in your organizations.</span></span> <span data-ttu-id="2bbb7-106">包括音訊檔需求。</span><span class="sxs-lookup"><span data-stu-id="2bbb7-106">Includes audio file requirements.</span></span>

<span data-ttu-id="2bbb7-107">商務用 Skype Server 宣告應用程式可讓您設定撥入電話號碼對您的組織有效，但不會指派給使用者或電話。</span><span class="sxs-lookup"><span data-stu-id="2bbb7-107">The Skype for Business Server Announcement application enables you to configure the handling of incoming phone calls when the dialed number is valid for your organization, but is not assigned to a user or a phone.</span></span> <span data-ttu-id="2bbb7-108">您可以將這些來電轉接至預先定義的目的地（電話號碼、SIP URI 或語音信箱），或播放音訊公告或兩者。</span><span class="sxs-lookup"><span data-stu-id="2bbb7-108">You can transfer these calls to a predetermined destination (phone number, SIP URI, or voice mail), or play an audio announcement, or both.</span></span> <span data-ttu-id="2bbb7-109">宣告應用程式可協助您避免來電者 misdials 和聽到忙音或 SIP 用戶端收到錯誤訊息的情況。</span><span class="sxs-lookup"><span data-stu-id="2bbb7-109">The Announcement application helps you avoid the situations in which a caller misdials and hears a busy tone or the SIP client receives an error message.</span></span> <span data-ttu-id="2bbb7-110">本節包含宣告應用程式專用的規劃資訊</span><span class="sxs-lookup"><span data-stu-id="2bbb7-110">This section includes planning information that is specific to the Announcement application</span></span>

<span data-ttu-id="2bbb7-111">當您部署宣告應用程式時，您必須設定 [未指定的數位] 資料表，決定當有人撥打未指派的號碼時所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="2bbb7-111">When you deploy the Announcement application, you need to configure an unassigned number table that determines the action to be taken when someone dials an unassigned number.</span></span> <span data-ttu-id="2bbb7-112">[未指定的數位] 表格包含適用于組織的電話號碼範圍，並指定哪個宣告應用程式會處理每個範圍。</span><span class="sxs-lookup"><span data-stu-id="2bbb7-112">The unassigned number table contains ranges of phone numbers that are valid for the organization and specifies which Announcement application handles each range.</span></span> <span data-ttu-id="2bbb7-113">當來電者撥打電話給您的組織而言，但不是指派給任何人時，商務用 Skype 伺服器會在未指定的數位路由表中尋找該號碼，找出該數位的範圍，並將呼叫路由到為該範圍指定的宣告應用程式。</span><span class="sxs-lookup"><span data-stu-id="2bbb7-113">When a caller dials a telephone number that is valid for your organization but is not assigned to anyone, Skype for Business Server looks up the number in the unassigned number routing table, identifies which range the number falls in, and routes the call to the Announcement application specified for that range.</span></span> <span data-ttu-id="2bbb7-114">[宣告] 應用程式會應答通話並播放音訊訊息（如果您將它設定為這樣做），然後中斷通話，或將它轉移至預先確定的目的地，例如操作員。</span><span class="sxs-lookup"><span data-stu-id="2bbb7-114">The Announcement application answers the call and plays an audio message (if you configured it to do so) and then either disconnects the call or transfers it to a predetermined destination, such as to an operator.</span></span> <span data-ttu-id="2bbb7-115">您可以使用商務用 Skype Server Management Shell Cmdlet 來設定多個音訊訊息或傳輸目的地。</span><span class="sxs-lookup"><span data-stu-id="2bbb7-115">You can use Skype for Business Server Management Shell cmdlets to configure multiple audio messages or to transfer destinations.</span></span>

<span data-ttu-id="2bbb7-116">設定未指派號碼表的方式取決於其使用方式。</span><span class="sxs-lookup"><span data-stu-id="2bbb7-116">How you configure the unassigned number table depends on how you want to use it.</span></span> <span data-ttu-id="2bbb7-117">如果您的特定號碼已不再使用，而您想要播放專為每個數位提供的訊息，您可以在 [未指定的數位] 資料表中輸入那些特定的數位。</span><span class="sxs-lookup"><span data-stu-id="2bbb7-117">If you have specific numbers that are no longer in use and you want to play messages that are tailored for each number, you can enter those specific numbers in the unassigned number table.</span></span> <span data-ttu-id="2bbb7-118">例如，如果您變更了客戶服務服務台的號碼，您可以輸入舊的客戶服務號碼，並將其與提供新號碼的公告建立關聯。</span><span class="sxs-lookup"><span data-stu-id="2bbb7-118">For example, if you changed the number for your customer service desk, you can enter the old customer service number and associate it with an announcement that gives the new number.</span></span> <span data-ttu-id="2bbb7-119">如果您想要在呼叫未獲指派之號碼的任何人（例如，針對離開貴組織的員工）發出一般訊息，您可以為組織中的所有有效延伸輸入範圍。</span><span class="sxs-lookup"><span data-stu-id="2bbb7-119">If you want to play a general message to anyone who calls a number that is not assigned, such as for employees who have left your organization, you can enter ranges for all the valid extensions in your organization.</span></span> <span data-ttu-id="2bbb7-120">每當來電者撥打目前未指派的號碼時，就會呼叫 [未指定的數位] 資料表。</span><span class="sxs-lookup"><span data-stu-id="2bbb7-120">The unassigned number table is invoked whenever the caller dials a number that is not currently assigned.</span></span>

## <a name="deployment-and-requirements"></a><span data-ttu-id="2bbb7-121">部署與需求</span><span class="sxs-lookup"><span data-stu-id="2bbb7-121">Deployment and requirements</span></span>

<span data-ttu-id="2bbb7-122">宣告應用程式會自動與回應群組應用程式一起安裝。</span><span class="sxs-lookup"><span data-stu-id="2bbb7-122">Tthe Announcement application is automatically installed with the Response Group application.</span></span> <span data-ttu-id="2bbb7-123">宣告與回應群組應用程式是企業語音部署的標準元件：當您部署企業語音時，這兩個應用程式都會自動部署。</span><span class="sxs-lookup"><span data-stu-id="2bbb7-123">The Announcement and Response Group applications are standard components of an Enterprise Voice deployment: When you deploy Enterprise Voice, both of these applications are automatically deployed.</span></span>

### <a name="software-requirements"></a><span data-ttu-id="2bbb7-124">軟體需求</span><span class="sxs-lookup"><span data-stu-id="2bbb7-124">Software requirements</span></span>

<span data-ttu-id="2bbb7-125">執行宣告應用程式的所有前端伺服器或標準版伺服器，都必須針對執行 Windows Server 2008 R2 的伺服器安裝 windows Media 格式執行時間，或是執行 Windows Server 2012 的伺服器的 Microsoft Media Foundation，或Windows Server 2012 R2。</span><span class="sxs-lookup"><span data-stu-id="2bbb7-125">All Front End Servers or Standard Edition servers that run the Announcement application must have the Windows Media Format Runtime installed for servers running Windows Server 2008 R2, or Microsoft Media Foundation for servers running Windows Server 2012 or Windows Server 2012 R2.</span></span> <span data-ttu-id="2bbb7-126">針對 Windows Server 2008 R2，Windows Media 格式執行時間會安裝為 Windows 桌面體驗的一部分。</span><span class="sxs-lookup"><span data-stu-id="2bbb7-126">For Windows Server 2008 R2, the Windows Media Format Runtime is installed as part of Windows Desktop Experience.</span></span> <span data-ttu-id="2bbb7-127">Windows Media 格式執行時間或 Microsoft 媒體基礎是 Windows Media 音訊（.wma）檔案所必需的，這些檔案是宣告應用程式在公告和音樂中播放的檔。</span><span class="sxs-lookup"><span data-stu-id="2bbb7-127">Windows Media Format Runtime or Microsoft Media Foundation is required for Windows Media Audio (.wma) files that the Announcement application plays for announcements and music.</span></span>

### <a name="port-requirements"></a><span data-ttu-id="2bbb7-128">埠需求</span><span class="sxs-lookup"><span data-stu-id="2bbb7-128">Port Requirements</span></span>

<span data-ttu-id="2bbb7-129">宣告應用程式使用**埠 5071**進行 SIP 偵聽要求。</span><span class="sxs-lookup"><span data-stu-id="2bbb7-129">The Announcement application uses **Port 5071** for SIP listening requests.</span></span>

> [!NOTE]
> <span data-ttu-id="2bbb7-130">這個埠是預設設定，您可以使用**CsApplicationServer** Cmdlet 進行變更。</span><span class="sxs-lookup"><span data-stu-id="2bbb7-130">This port is the default setting, which you can change by using the **Set-CsApplicationServer** cmdlet.</span></span> <span data-ttu-id="2bbb7-131">如需此 Cmdlet 的詳細資訊，請參閱商務用 Skype Server 管理命令介面檔。</span><span class="sxs-lookup"><span data-stu-id="2bbb7-131">For details about this cmdlet, see the Skype for Business Server Management Shell documentation.</span></span>

### <a name="audio-file-requirements"></a><span data-ttu-id="2bbb7-132">音訊檔需求</span><span class="sxs-lookup"><span data-stu-id="2bbb7-132">Audio File Requirements</span></span>

<span data-ttu-id="2bbb7-133">宣告應用程式支援 Wave （.wav）檔案格式和 Windows Media 音訊（.wma）檔案格式，以供音樂和公告用。</span><span class="sxs-lookup"><span data-stu-id="2bbb7-133">The Announcement application supports Wave (.wav) file format and Windows Media audio (.wma) file format for music and announcements.</span></span> <span data-ttu-id="2bbb7-134">宣告應用程式的音訊檔需求與回應群組應用程式相同。</span><span class="sxs-lookup"><span data-stu-id="2bbb7-134">Audio file requirements for the Announcement application are the same as for the Response Group application.</span></span> <span data-ttu-id="2bbb7-135">如需詳細資訊，請參閱[回應群組的技術需求](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)。</span><span class="sxs-lookup"><span data-stu-id="2bbb7-135">For details, see [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx).</span></span>


