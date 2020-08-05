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
description: 瞭解如何設定 Exchange 混合式組織以搭配 Microsoft 團隊使用，以確保群組成員資格已同步處理。
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1061ce633dcd1db8f956a37143850deed9855e56
ms.sourcegitcommit: ab094058e3ffa974527fce8a331dad609ac19609
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/04/2020
ms.locfileid: "46551959"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a>設定 Exchange 混合式組織以搭配 Microsoft 團隊使用
======================================================================

一般來說，您不需要設定任何 Exchange Online 功能即可與 Microsoft 團隊搭配使用。 不過，針對 Exchange 混合式案例，您必須採取一些步驟，以確保在 Exchange Server (內部部署) 與 Exchange Online 之間同步處理群組成員資格。 這涉及在 Azure AD Connect 中啟用群組寫回功能，以及各種初始化腳本：[將 Microsoft 365 群組與內部部署 Exchange 混合](https://docs.microsoft.com/exchange/hybrid-deployment/set-up-microsoft-365-groups)式搭配使用。
