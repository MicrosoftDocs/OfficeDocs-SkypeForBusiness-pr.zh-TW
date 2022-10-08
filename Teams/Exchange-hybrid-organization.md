---
title: 設定 Exchange 混合式組織
author: JoanneHendrickson
ms.author: jhendr
manager: serdars
ms.date: 09/25/2017
ms.topic: article
audience: admin
ms.service: msteams
description: 瞭解如何設定 Exchange 混合式組織，以搭配 Microsoft Teams 使用，以確保同步處理群組成員資格。
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cb2471a2680218a69daa74d20b27c4b7642fa1d7
ms.sourcegitcommit: fc87f4300f53abf7a049936944abb21d0cade0d9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/06/2022
ms.locfileid: "68480673"
---
# <a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a>設定 Exchange 混合式組織以搭配 Microsoft Teams 使用

一般而言，您不需要設定任何與 Microsoft Teams 搭配使用的Exchange Online功能。 不過，對於 Exchange 混合式案例，必須採取一些步驟，確保Exchange Server (內部部署) 和Exchange Online之間已同步處理群組成員資格。 這涉及啟用 Azure AD Connect 中的群組回寫功能，以及各種初始化腳本：[使用內部部署 Exchange 混合式設定Microsoft 365 群組](/exchange/hybrid-deployment/set-up-microsoft-365-groups)。