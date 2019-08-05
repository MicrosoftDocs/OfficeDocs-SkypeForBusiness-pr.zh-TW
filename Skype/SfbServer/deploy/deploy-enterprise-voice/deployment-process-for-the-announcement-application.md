---
title: 商務用 Skype Server 中宣告應用程式的部署程式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
description: 在商務用 Skype Server Enterprise Voice 中發佈應用程式的部署程式和步驟。
ms.openlocfilehash: 77d15c4ce749a97ec11ed5d5e083ccf6fa2aecfa
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187339"
---
# <a name="deployment-process-for-the-announcement-application-in-skype-for-business-server"></a><span data-ttu-id="d9fe2-103">商務用 Skype Server 中宣告應用程式的部署程式</span><span class="sxs-lookup"><span data-stu-id="d9fe2-103">Deployment process for the Announcement application in Skype for Business Server</span></span>
 
<span data-ttu-id="d9fe2-104">在商務用 Skype Server Enterprise Voice 中發佈應用程式的部署程式和步驟。</span><span class="sxs-lookup"><span data-stu-id="d9fe2-104">Deployment process and steps for Announcement application in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="d9fe2-105">[宣告] 應用程式是一種企業語音功能, 可讓您設定呼叫未指派的延伸 (對貴組織有效, 但未指派給人員或電話的延伸)。</span><span class="sxs-lookup"><span data-stu-id="d9fe2-105">The Announcement application is an Enterprise Voice feature that enables you to configure what happens to calls to unassigned extensions (extensions that are valid for your organization, but are not assigned to a person or a phone).</span></span> <span data-ttu-id="d9fe2-106">例如, 您可以設定未指派號碼的呼叫來播放郵件, 或將其傳送至不同的目的地, 或兩者皆可。</span><span class="sxs-lookup"><span data-stu-id="d9fe2-106">For example, you can configure calls to unassigned numbers to play a message, or to be transferred to a different destination, or both.</span></span>
  
<span data-ttu-id="d9fe2-107">發佈應用程式是在您部署企業語音時, 在前端伺服器或標準版伺服器上作為回應群組應用程式的功能安裝。</span><span class="sxs-lookup"><span data-stu-id="d9fe2-107">The Announcement application is installed as a feature of Response Group application on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="d9fe2-108">您必須先上傳音訊檔案或設定文字轉換語音 (TTS) 及設定 [未指定的數位] 資料表來設定宣告。</span><span class="sxs-lookup"><span data-stu-id="d9fe2-108">You need to configure Announcements by uploading your audio files or by configuring text-to-speech (TTS) and configuring the unassigned number table.</span></span>
  
<span data-ttu-id="d9fe2-109">本節概要說明部署宣告應用程式所需的步驟。</span><span class="sxs-lookup"><span data-stu-id="d9fe2-109">This section provides an overview of the steps involved in deploying the Announcement application.</span></span> <span data-ttu-id="d9fe2-110">您必須先部署企業語音, 然後才能設定宣告。</span><span class="sxs-lookup"><span data-stu-id="d9fe2-110">You must deploy Enterprise Voice before you configure announcements.</span></span> <span data-ttu-id="d9fe2-111">當您部署企業語音時, 會安裝並啟用宣告應用程式所需的元件。</span><span class="sxs-lookup"><span data-stu-id="d9fe2-111">The components required by the Announcement application are installed and enabled when you deploy Enterprise Voice.</span></span>
  
<span data-ttu-id="d9fe2-112">**發佈部署程式**</span><span class="sxs-lookup"><span data-stu-id="d9fe2-112">**Announcement Deployment Process**</span></span>

|<span data-ttu-id="d9fe2-113">**分**</span><span class="sxs-lookup"><span data-stu-id="d9fe2-113">**Phase**</span></span>|<span data-ttu-id="d9fe2-114">**步驟**</span><span class="sxs-lookup"><span data-stu-id="d9fe2-114">**Steps**</span></span>|<span data-ttu-id="d9fe2-115">**角色**</span><span class="sxs-lookup"><span data-stu-id="d9fe2-115">**Roles**</span></span>|<span data-ttu-id="d9fe2-116">**部署檔**</span><span class="sxs-lookup"><span data-stu-id="d9fe2-116">**Deployment documentation**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d9fe2-117">設定宣告設定</span><span class="sxs-lookup"><span data-stu-id="d9fe2-117">Configure Announcement settings</span></span>  <br/> | <span data-ttu-id="d9fe2-118">透過錄製及上傳音訊檔案或使用文字轉換語音 (TTS) 來建立公告。</span><span class="sxs-lookup"><span data-stu-id="d9fe2-118">Create the announcement by recording and uploading audio files or by using text-to-speech (TTS).</span></span> <br/>  <span data-ttu-id="d9fe2-119">在 [未指定的數位] 資料表中設定未指定的數位範圍, 並將它們與適當的宣告建立關聯。</span><span class="sxs-lookup"><span data-stu-id="d9fe2-119">Configure the unassigned number ranges in the unassigned number table and associate them with the appropriate announcement.</span></span> <br/> |<span data-ttu-id="d9fe2-120">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="d9fe2-120">RTCUniversalServerAdmins</span></span>  <br/> <span data-ttu-id="d9fe2-121">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="d9fe2-121">CsVoiceAdministrator</span></span>  <br/> <span data-ttu-id="d9fe2-122">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="d9fe2-122">CsServerAdministrator</span></span>  <br/> <span data-ttu-id="d9fe2-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="d9fe2-123">CsAdministrator</span></span>  <br/> <span data-ttu-id="d9fe2-124">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="d9fe2-124">CsViewOnlyAdministrator</span></span>  <br/> |[<span data-ttu-id="d9fe2-125">在商務用 Skype Server 中建立或刪除公告</span><span class="sxs-lookup"><span data-stu-id="d9fe2-125">Create or delete an announcement in Skype for Business Server</span></span>](create-an-announcement.md) <br/> [<span data-ttu-id="d9fe2-126">在商務用 Skype Server 中建立或修改未指定的數位範圍</span><span class="sxs-lookup"><span data-stu-id="d9fe2-126">Create or modify an unassigned number range in Skype for Business Server</span></span>](create-or-modify-an-unassigned-number-range.md) <br/> |
|<span data-ttu-id="d9fe2-127">確認您的宣告部署</span><span class="sxs-lookup"><span data-stu-id="d9fe2-127">Verify your Announcement deployment</span></span>  <br/> |<span data-ttu-id="d9fe2-128">透過聆聽宣告來測試, 以確認您的設定如預期的那樣正常運作。</span><span class="sxs-lookup"><span data-stu-id="d9fe2-128">Test by listening to announcements to verify that your configuration works as expected.</span></span>  <br/> |-  <br/> |[<span data-ttu-id="d9fe2-129">可選在商務用 Skype 中驗證宣告部署</span><span class="sxs-lookup"><span data-stu-id="d9fe2-129">(Optional) Verify Announcement deployment in Skype for Business</span></span>](optional-verify-announcement-deployment.md) <br/> |
   

