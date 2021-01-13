---
title: 商務用 Skype Server 中宣告應用程式的部署程式
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
description: 在商務用 Skype Server Enterprise Voice 中宣告應用程式的部署程式和步驟。
ms.openlocfilehash: cfb1436f22681b45de5c399907d4776a9d1db5de
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812303"
---
# <a name="deployment-process-for-the-announcement-application-in-skype-for-business-server"></a><span data-ttu-id="bc003-103">商務用 Skype Server 中宣告應用程式的部署程式</span><span class="sxs-lookup"><span data-stu-id="bc003-103">Deployment process for the Announcement application in Skype for Business Server</span></span>
 
<span data-ttu-id="bc003-104">在商務用 Skype Server Enterprise Voice 中宣告應用程式的部署程式和步驟。</span><span class="sxs-lookup"><span data-stu-id="bc003-104">Deployment process and steps for Announcement application in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="bc003-105">宣告應用程式是一種企業語音功能，可讓您設定呼叫未指派的分機號碼 (對組織有效的分機，但未指派給人員或電話) 。</span><span class="sxs-lookup"><span data-stu-id="bc003-105">The Announcement application is an Enterprise Voice feature that enables you to configure what happens to calls to unassigned extensions (extensions that are valid for your organization, but are not assigned to a person or a phone).</span></span> <span data-ttu-id="bc003-106">例如，您可以設定撥給未指派號碼的來電，以播放訊息或轉接至不同目的地，或兩者。</span><span class="sxs-lookup"><span data-stu-id="bc003-106">For example, you can configure calls to unassigned numbers to play a message, or to be transferred to a different destination, or both.</span></span>
  
<span data-ttu-id="bc003-107">當您部署企業語音時，會將宣告應用程式安裝為前端伺服器或 Standard Edition Server 上的回應群組應用程式功能。</span><span class="sxs-lookup"><span data-stu-id="bc003-107">The Announcement application is installed as a feature of Response Group application on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="bc003-108">您需要設定宣告，作法為上傳音訊檔案或設定文字轉換語音 (TTS)，以及設定未指派的號碼表。</span><span class="sxs-lookup"><span data-stu-id="bc003-108">You need to configure Announcements by uploading your audio files or by configuring text-to-speech (TTS) and configuring the unassigned number table.</span></span>
  
<span data-ttu-id="bc003-109">本節概述部署宣告應用程式所需的步驟。</span><span class="sxs-lookup"><span data-stu-id="bc003-109">This section provides an overview of the steps involved in deploying the Announcement application.</span></span> <span data-ttu-id="bc003-110">您必須先部署 Enterprise Voice，才能設定宣告。</span><span class="sxs-lookup"><span data-stu-id="bc003-110">You must deploy Enterprise Voice before you configure announcements.</span></span> <span data-ttu-id="bc003-111">當您部署企業語音時，會安裝並啟用宣告應用程式所需的元件。</span><span class="sxs-lookup"><span data-stu-id="bc003-111">The components required by the Announcement application are installed and enabled when you deploy Enterprise Voice.</span></span>
  
<span data-ttu-id="bc003-112">**宣告部署程序**</span><span class="sxs-lookup"><span data-stu-id="bc003-112">**Announcement Deployment Process**</span></span>

|<span data-ttu-id="bc003-113">**階段**</span><span class="sxs-lookup"><span data-stu-id="bc003-113">**Phase**</span></span>|<span data-ttu-id="bc003-114">**步驟**</span><span class="sxs-lookup"><span data-stu-id="bc003-114">**Steps**</span></span>|<span data-ttu-id="bc003-115">**角色**</span><span class="sxs-lookup"><span data-stu-id="bc003-115">**Roles**</span></span>|<span data-ttu-id="bc003-116">**部署文件**</span><span class="sxs-lookup"><span data-stu-id="bc003-116">**Deployment documentation**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bc003-117">設定宣告設定</span><span class="sxs-lookup"><span data-stu-id="bc003-117">Configure Announcement settings</span></span>  <br/> | <span data-ttu-id="bc003-118">錄製及上傳音訊檔案，或是使用文字轉語音 (TTS)，以建立宣告。</span><span class="sxs-lookup"><span data-stu-id="bc003-118">Create the announcement by recording and uploading audio files or by using text-to-speech (TTS).</span></span> <br/>  <span data-ttu-id="bc003-119">設定未指派號碼表格中的未指派號碼範圍，並建立它們與適當宣告的關聯。</span><span class="sxs-lookup"><span data-stu-id="bc003-119">Configure the unassigned number ranges in the unassigned number table and associate them with the appropriate announcement.</span></span> <br/> |<span data-ttu-id="bc003-120">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="bc003-120">RTCUniversalServerAdmins</span></span>  <br/> <span data-ttu-id="bc003-121">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="bc003-121">CsVoiceAdministrator</span></span>  <br/> <span data-ttu-id="bc003-122">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="bc003-122">CsServerAdministrator</span></span>  <br/> <span data-ttu-id="bc003-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="bc003-123">CsAdministrator</span></span>  <br/> <span data-ttu-id="bc003-124">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="bc003-124">CsViewOnlyAdministrator</span></span>  <br/> |[<span data-ttu-id="bc003-125">在商務用 Skype Server 中建立或刪除宣告</span><span class="sxs-lookup"><span data-stu-id="bc003-125">Create or delete an announcement in Skype for Business Server</span></span>](create-an-announcement.md) <br/> [<span data-ttu-id="bc003-126">在商務用 Skype Server 中建立或修改未指派號碼範圍</span><span class="sxs-lookup"><span data-stu-id="bc003-126">Create or modify an unassigned number range in Skype for Business Server</span></span>](create-or-modify-an-unassigned-number-range.md) <br/> |
|<span data-ttu-id="bc003-127">驗證宣告部署</span><span class="sxs-lookup"><span data-stu-id="bc003-127">Verify your Announcement deployment</span></span>  <br/> |<span data-ttu-id="bc003-128">透過接聽宣告以驗證設定如預期運作。</span><span class="sxs-lookup"><span data-stu-id="bc003-128">Test by listening to announcements to verify that your configuration works as expected.</span></span>  <br/> |-  <br/> |[<span data-ttu-id="bc003-129"> (選用) 在商務用 Skype 中驗證宣告部署</span><span class="sxs-lookup"><span data-stu-id="bc003-129">(Optional) Verify Announcement deployment in Skype for Business</span></span>](optional-verify-announcement-deployment.md) <br/> |
   

