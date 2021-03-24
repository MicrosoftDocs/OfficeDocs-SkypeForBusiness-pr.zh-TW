---
title: 新增 Office Web Apps Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddOfficeWebAppsServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
ROBOTS: NOINDEX, NOFOLLOW
description: '[定義新的 Office Web Apps Server] 嚮導會在您的部署中定義新的 Office Web Apps Server。 您填寫下列資訊：'
ms.openlocfilehash: 84ebc3b3ca7a413d81b4a36e62cc33a4f3fd91f0
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095777"
---
# <a name="add-office-web-apps-server"></a>新增 Office Web Apps Server

[ **定義新的 Office Web Apps server** ] 嚮導會在您的部署中定義新的 Office Web apps server。 您填寫下列資訊：

 **Office Web Apps SERVER FQDN**：輸入將主控 Office Web Apps Server 之伺服器的完整功能變數名稱

 **Office Web Apps server 探索 URL**：輸入 Office Web apps server 的完整統一資源定位器 (URL) 

> [!TIP]
> **Office Web Apps server 探索 URL** 的預設行為是以 Office Web apps SERVER 的 FQDN 為基礎，以下列格式建立 URL： `https://<FQDN of the Office Web Apps Server/hosting/discovery` 。 在大多數的情況下，您不需要變更預設的格式。 如果 Office Web Apps Server 和 Office Web Apps Server 探索 URL 必須不同，您可能需要變更預設的格式。 例如，您的 Office Web Apps Server 位於周邊網路中，而且會根據位置而有不同的 URL。

 **Office Web Apps server 部署在外部網路 (，也就是周邊/網際網路)**：如果您的 Office Web apps server 位於內部防火牆之外，例如周邊網路、外部網路或其他與您的內部網路不同的網路區域，請選取此核取方塊。

## <a name="see-also"></a>另請參閱

[會議的元件和拓撲](/previous-versions/office/lync-server-2013/lync-server-2013-components-and-topologies-for-conferencing)