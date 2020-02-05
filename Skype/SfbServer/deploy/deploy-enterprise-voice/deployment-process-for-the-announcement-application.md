---
title: 商務用 Skype Server 中宣告應用程式的部署程式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 在商務用 Skype Server Enterprise Voice 中發佈應用程式的部署程式和步驟。
ms.openlocfilehash: 89f01ed4c9488aa74b07bfae41f3bf27032b552e
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767396"
---
# <a name="deployment-process-for-the-announcement-application-in-skype-for-business-server"></a><span data-ttu-id="9d72c-103">商務用 Skype Server 中宣告應用程式的部署程式</span><span class="sxs-lookup"><span data-stu-id="9d72c-103">Deployment process for the Announcement application in Skype for Business Server</span></span>
 
<span data-ttu-id="9d72c-104">在商務用 Skype Server Enterprise Voice 中發佈應用程式的部署程式和步驟。</span><span class="sxs-lookup"><span data-stu-id="9d72c-104">Deployment process and steps for Announcement application in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="9d72c-105">[宣告] 應用程式是一種企業語音功能，可讓您設定呼叫未指派的延伸（對貴組織有效，但未指派給人員或電話的延伸）。</span><span class="sxs-lookup"><span data-stu-id="9d72c-105">The Announcement application is an Enterprise Voice feature that enables you to configure what happens to calls to unassigned extensions (extensions that are valid for your organization, but are not assigned to a person or a phone).</span></span> <span data-ttu-id="9d72c-106">例如，您可以設定未指派號碼的呼叫來播放郵件，或將其傳送至不同的目的地，或兩者皆可。</span><span class="sxs-lookup"><span data-stu-id="9d72c-106">For example, you can configure calls to unassigned numbers to play a message, or to be transferred to a different destination, or both.</span></span>
  
<span data-ttu-id="9d72c-107">發佈應用程式是在您部署企業語音時，在前端伺服器或標準版伺服器上作為回應群組應用程式的功能安裝。</span><span class="sxs-lookup"><span data-stu-id="9d72c-107">The Announcement application is installed as a feature of Response Group application on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="9d72c-108">您必須先上傳音訊檔案或設定文字轉換語音（TTS）及設定 [未指定的數位] 資料表來設定宣告。</span><span class="sxs-lookup"><span data-stu-id="9d72c-108">You need to configure Announcements by uploading your audio files or by configuring text-to-speech (TTS) and configuring the unassigned number table.</span></span>
  
<span data-ttu-id="9d72c-109">本節概要說明部署宣告應用程式所需的步驟。</span><span class="sxs-lookup"><span data-stu-id="9d72c-109">This section provides an overview of the steps involved in deploying the Announcement application.</span></span> <span data-ttu-id="9d72c-110">您必須先部署企業語音，然後才能設定宣告。</span><span class="sxs-lookup"><span data-stu-id="9d72c-110">You must deploy Enterprise Voice before you configure announcements.</span></span> <span data-ttu-id="9d72c-111">當您部署企業語音時，會安裝並啟用宣告應用程式所需的元件。</span><span class="sxs-lookup"><span data-stu-id="9d72c-111">The components required by the Announcement application are installed and enabled when you deploy Enterprise Voice.</span></span>
  
<span data-ttu-id="9d72c-112">**發佈部署程式**</span><span class="sxs-lookup"><span data-stu-id="9d72c-112">**Announcement Deployment Process**</span></span>

|<span data-ttu-id="9d72c-113">**分**</span><span class="sxs-lookup"><span data-stu-id="9d72c-113">**Phase**</span></span>|<span data-ttu-id="9d72c-114">**步驟**</span><span class="sxs-lookup"><span data-stu-id="9d72c-114">**Steps**</span></span>|<span data-ttu-id="9d72c-115">**角色**</span><span class="sxs-lookup"><span data-stu-id="9d72c-115">**Roles**</span></span>|<span data-ttu-id="9d72c-116">**部署檔**</span><span class="sxs-lookup"><span data-stu-id="9d72c-116">**Deployment documentation**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9d72c-117">設定宣告設定</span><span class="sxs-lookup"><span data-stu-id="9d72c-117">Configure Announcement settings</span></span>  <br/> | <span data-ttu-id="9d72c-118">透過錄製及上傳音訊檔案或使用文字轉換語音（TTS）來建立公告。</span><span class="sxs-lookup"><span data-stu-id="9d72c-118">Create the announcement by recording and uploading audio files or by using text-to-speech (TTS).</span></span> <br/>  <span data-ttu-id="9d72c-119">在 [未指定的數位] 資料表中設定未指定的數位範圍，並將它們與適當的宣告建立關聯。</span><span class="sxs-lookup"><span data-stu-id="9d72c-119">Configure the unassigned number ranges in the unassigned number table and associate them with the appropriate announcement.</span></span> <br/> |<span data-ttu-id="9d72c-120">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="9d72c-120">RTCUniversalServerAdmins</span></span>  <br/> <span data-ttu-id="9d72c-121">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="9d72c-121">CsVoiceAdministrator</span></span>  <br/> <span data-ttu-id="9d72c-122">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="9d72c-122">CsServerAdministrator</span></span>  <br/> <span data-ttu-id="9d72c-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="9d72c-123">CsAdministrator</span></span>  <br/> <span data-ttu-id="9d72c-124">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="9d72c-124">CsViewOnlyAdministrator</span></span>  <br/> |[<span data-ttu-id="9d72c-125">在商務用 Skype Server 中建立或刪除公告</span><span class="sxs-lookup"><span data-stu-id="9d72c-125">Create or delete an announcement in Skype for Business Server</span></span>](create-an-announcement.md) <br/> [<span data-ttu-id="9d72c-126">在商務用 Skype Server 中建立或修改未指定的數位範圍</span><span class="sxs-lookup"><span data-stu-id="9d72c-126">Create or modify an unassigned number range in Skype for Business Server</span></span>](create-or-modify-an-unassigned-number-range.md) <br/> |
|<span data-ttu-id="9d72c-127">確認您的宣告部署</span><span class="sxs-lookup"><span data-stu-id="9d72c-127">Verify your Announcement deployment</span></span>  <br/> |<span data-ttu-id="9d72c-128">透過聆聽宣告來測試，以確認您的設定如預期的那樣正常運作。</span><span class="sxs-lookup"><span data-stu-id="9d72c-128">Test by listening to announcements to verify that your configuration works as expected.</span></span>  <br/> |-  <br/> |[<span data-ttu-id="9d72c-129">可選在商務用 Skype 中驗證宣告部署</span><span class="sxs-lookup"><span data-stu-id="9d72c-129">(Optional) Verify Announcement deployment in Skype for Business</span></span>](optional-verify-announcement-deployment.md) <br/> |
   

