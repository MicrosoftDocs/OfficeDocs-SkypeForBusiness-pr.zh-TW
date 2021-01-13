---
title: 建立前端與 AV MCU 的關聯
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AssociateFrontEndWithAvMcuPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 314e3b0b-9ca7-423b-9c8e-80eb6013d36f
ROBOTS: NOINDEX, NOFOLLOW
description: A/V 會議讓使用者之間得以進行即時的音訊和視訊通訊 (但他們需要有適當的用戶端裝置，例如音訊會議需要有耳機，而視訊會議需要有網路攝影機)。 如果您的部署支援會議，且您同時啟用 Web 會議和 A/V 會議，則您可以組合 A/V 會議伺服器與前端伺服器，也可以部署一或多個獨立的 A/V 會議伺服器 (A/V 會議集區)。 如果您選擇部署獨立 A/V 會議伺服器的選項，您必須在拓撲產生器中定義此選項。
ms.openlocfilehash: 24aec4c97b1d9a0f30ef8e775d04b93d7de4fec2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49811423"
---
# <a name="associate-front-end-with-av-mcu"></a><span data-ttu-id="72db1-105">建立前端與 AV MCU 的關聯</span><span class="sxs-lookup"><span data-stu-id="72db1-105">Associate Front End With AV MCU</span></span>
 
<span data-ttu-id="72db1-106">A/V 會議讓使用者之間得以進行即時的音訊和視訊通訊 (但他們需要有適當的用戶端裝置，例如音訊會議需要有耳機，而視訊會議需要有網路攝影機)。</span><span class="sxs-lookup"><span data-stu-id="72db1-106">A/V Conferencing enables real-time audio and video communications between your users (that is, if they have appropriate client devices, such as headsets for audio conferences, and webcams for video conferences).</span></span> <span data-ttu-id="72db1-107">如果您的部署支援會議，且您同時啟用 Web 會議和 A/V 會議，則您可以組合 A/V 會議伺服器與前端伺服器，也可以部署一或多個獨立的 A/V 會議伺服器 (A/V 會議集區)。</span><span class="sxs-lookup"><span data-stu-id="72db1-107">If your deployment supports conferencing and you enable both web conferencing and A/V Conferencing, you can collocate the A/V Conferencing Server with the Front End Server), or you can deploy one or more stand-alone A/V Conferencing Servers (A/V Conferencing pool).</span></span> <span data-ttu-id="72db1-108">如果您選擇部署獨立 A/V 會議伺服器的選項，您必須在拓撲產生器中定義此選項。</span><span class="sxs-lookup"><span data-stu-id="72db1-108">If you choose the option to deploy a stand-alone A/V Conferencing Server, you must define it in Topology Builder.</span></span>
  
<span data-ttu-id="72db1-109">如果使用不超過 A/V 會議伺服器的容量，則網站上的所有集區和多個中央網站的集區可以使用相同的 A/V 會議伺服器。</span><span class="sxs-lookup"><span data-stu-id="72db1-109">All pools at a site and the pools of multiple central sites can use the same A/V Conferencing Server, if usage does not exceed the capacity of the A/V Conferencing Server.</span></span> 
  

