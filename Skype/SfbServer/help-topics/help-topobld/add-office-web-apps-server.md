---
title: 新增 Office Web Apps Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddOfficeWebAppsServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
description: '[定義新的 Office Web Apps 伺服器] 嚮導會在您的部署中定義新的 Office Web Apps 伺服器。 您填入下列資訊：'
ms.openlocfilehash: 9f0d9680e57dd55b0a4370364aff23c7f37f57a4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820715"
---
# <a name="add-office-web-apps-server"></a>新增 Office Web Apps Server

[**定義新的 Office Web Apps 伺服器**] 嚮導會在您的部署中定義新的 Office Web apps 伺服器。 您填入下列資訊：

 **Office Web Apps 伺服器 FQDN**：輸入將裝載 Office Web Apps 伺服器之伺服器的完整功能變數名稱

 **Office Web Apps Server 探索 URL**：輸入 Office Web apps 伺服器的完整統一資源定位器（URL）

> [!TIP]
> **Office Web Apps server 探索 URL**的預設行為是根據格式： `https://<FQDN of the Office Web Apps Server/hosting/discovery` ，以 Office WEB apps SERVER 的 FQDN 建立 URL。 在大部分的情況下，您不需要變更預設格式。 如果 Office Web Apps Server 和 Office Web Apps Server 探索 URL 必須不同，您可能需要變更預設格式。 例如，您的 Office Web Apps 伺服器位於周邊網路中，並且會根據位置使用不同的 URL。

 **Office Web Apps 伺服器已部署在外部網路（也就是 [周長/網際網路]）**：如果您的 Office Web apps 伺服器位於內部防火牆以外（例如周邊網路、外部網路或其他與您的內部網路不同的網路區域），請選取此核取方塊。

## <a name="see-also"></a>另請參閱

[會議的元件與拓撲](https://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)
