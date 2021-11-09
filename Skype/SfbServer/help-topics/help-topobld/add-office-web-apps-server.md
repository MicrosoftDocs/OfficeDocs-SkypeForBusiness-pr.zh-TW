---
title: 新增 Office Web Apps Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddOfficeWebAppsServerPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
description: 在您的部署中，[定義新的 Office Web apps server] 嚮導會定義新的 Office web apps server。 您填寫下列資訊：
ms.openlocfilehash: 8a2565788879b86677784e26458cfba39d165076
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60848766"
---
# <a name="add-office-web-apps-server"></a>新增 Office Web Apps Server

在您的部署中，[**定義新的 Office Web apps server** ] 嚮導會定義新的 Office web apps server。 您填寫下列資訊：

 **Office Web apps server FQDN**：輸入將主控 Office Web Apps Server 之伺服器的完整功能變數名稱

 **Office Web apps server 探索 URL**：輸入 Office Web apps server 的完整統一資源定位器 (URL) 

> [!TIP]
> **Office Web apps server 探索 URL** 的預設行為是，以 [格式：] 的 Office Web apps server 的 FQDN 建立 URL `https://<FQDN of the Office Web Apps Server/hosting/discovery` 。 在大多數的情況下，您不需要變更預設的格式。 當 Office web apps server 和 Office Web apps server 探索 URL 必須不同時，您可能需要變更預設的格式。 例如，您的 Office Web Apps Server 位於周邊網路中，而且會根據位置而有不同的 URL。

 **Office Web apps server 部署在外部網路 (，也就是周邊/網際網路)**：如果 Office 網頁應用程式伺服器是放在內部防火牆外面，例如周邊網路、外部網路或其他與您的內部網路不同的網路區域，請選取此核取方塊。

## <a name="see-also"></a>另請參閱

[會議的元件和拓撲](/previous-versions/office/lync-server-2013/lync-server-2013-components-and-topologies-for-conferencing)