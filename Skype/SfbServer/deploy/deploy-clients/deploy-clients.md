---
title: 針對商務用 Skype Server 部署用戶端
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: 摘要：商務用 Skype 的企業用戶端安裝方法概覽。
ms.openlocfilehash: b791a4f460eaeac86345eae8896046d90d88831b
ms.sourcegitcommit: ed3a6789dedf54275e0b1ab41d4a4230eed6eb72
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/30/2020
ms.locfileid: "41628289"
---
# <a name="deploy-clients-for-skype-for-business-server"></a>針對商務用 Skype Server 部署用戶端
 
**摘要：** 商務用 Skype 的企業用戶端安裝方法概覽。
  
如何將商務用 Skype 部署到您的使用者，取決於您是否已購買商務用 skype 作為 Office 365 方案的一部分，或是您購買了大量授權版的商務用 Skype。 
  
- **Office 365**如果您有包含商務用 Skype 的 Office 365 方案，則所使用的安裝技術稱為「隨選即用」。 有了 Office 365，您就可以讓使用者從 Office 365 入口網站自行安裝商務用 Skype。 或者，您可以將軟體下載到您的本機網路，然後使用您現有的軟體部署工具（例如 Microsoft 端點建構管理員），將商務用 Skype 部署到您的使用者。 如需 Office 365 隨附之商務用 Skype 的安裝資訊，請參閱[在 office 365 中部署商務用 skype 用戶端](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96)。
    
- **大量授權**如果您有大量授權版的商務用 Skype 2015 或2016用戶端，則使用的安裝技術是 Windows Installer （MSI）。 以 Windows 安裝程式為基礎的安裝套件由多個 MSI 檔案組成。 語言中立的核心 MSI 套件與一或多個語言特定套件結合，以製作完整的產品。 安裝程式會彙編個別套件，並在安裝使用者電腦上的 Office 期間和之後執行自訂及維護作業。 商務用 Skype 2019 用戶端使用「隨選即用」的安裝程式。
    
本節中的主題說明如何使用及自訂 Windows 安裝程式，以透過您的一般程式將商務用 Skype 用戶端部署到您的使用者。
  
> [!NOTE]
> Microsoft Office 的 Skype 會議增益集（支援 Outlook 訊息和共同作業用戶端中的會議管理）會自動安裝與商務用 Skype 用戶端。 
  
> [!NOTE]
> Office 365 安裝程式不會卸載舊版的 Lync。 商務用 Skype 用戶端會與其他 Lync 用戶端並排安裝。 
  
## <a name="installing-windows-clients"></a>安裝 Windows 用戶端

- [在商務用 Skype Server 中自訂 Windows 用戶端安裝](customize-windows-client-installation.md)
    
- [透過商務用 Skype 設定用戶端體驗](configure-the-client-experience.md)
    
- [在商務用 Skype Server 中設定智慧連絡人清單](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a>安裝裝置用戶端

- [安裝並測試 Windows Phone 版商務用 Skype](windows-phone.md)
    
- [安裝並測試 iOS 版商務用 Skype](ios.md)
    
    
- [使用商務用 Skype Server 部署 Lync VDI 外掛程式](deploy-the-lync-vdi-plug-in.md)
    
- [在商務用 Skype Server 中部署網頁下載用戶端](deploy-web-downloadable-clients.md)
    
- [在商務用 Skype 中自訂 Mac 用戶端體驗](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a>另請參閱

[在 Office 365 中部署商務用 Skype 用戶端](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)
