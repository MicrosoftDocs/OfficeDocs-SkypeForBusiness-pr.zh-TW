---
title: 設定 Exchange 混合式組織
author: dstrome
ms.author: dstrome
manager: serdars
ms.date: 09/25/2017
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: dstrome
description: 瞭解如何設定 Exchange 混合式組織，以與 Microsoft Teams 一起使用，以確保群組成員資格同步處理。
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 90250b3d3f3593990d356843bebea324060d6f8b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094605"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a>設定 Exchange 混合式組織以用於 Microsoft Teams
======================================================================

一般而言，您不應設定任何 Exchange Online 功能，以用於 Microsoft Teams。 不過，針對 Exchange 混合式案例，有一些必要步驟可確保 Exchange Server (內部部署和 Exchange Online) 同步處理群組成員資格。 這涉及啟用 Azure AD Connect 中的群組寫回功能，以及各種初始化腳本：使用內部部署 Exchange 混合式設定 [Microsoft 365 群組](/exchange/hybrid-deployment/set-up-microsoft-365-groups)。