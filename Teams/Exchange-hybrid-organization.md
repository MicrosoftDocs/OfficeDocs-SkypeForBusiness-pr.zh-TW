---
title: 設定 Exchange 混合式組織以搭配 Microsoft 團隊使用
author: dstrome
ms.author: dstrome
manager: serdars
ms.date: 09/25/2017
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: dstrome
description: 瞭解如何設定與 Microsoft 團隊搭配使用的 Exchange 混合式組織。
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: eb81460a5a3d388bc9634cb53ce15655933534c5
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41834443"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a>設定 Exchange 混合式組織以搭配 Microsoft 團隊使用
======================================================================

一般來說，您不需要設定任何 Exchange Online 功能即可與 Microsoft 團隊搭配使用。 不過，針對 Exchange 混合式案例，必須採取一些步驟，才能確保在 Exchange 伺服器（內部部署）與 Exchange Online 之間同步處理群組成員資格。 這包括啟用 Azure AD Connect 中的群組寫回功能，以及各種初始化腳本：[使用內部部署 Exchange 混合式來設定 Office 365 群組](https://go.microsoft.com/fwlink/?linkid=854389)。
