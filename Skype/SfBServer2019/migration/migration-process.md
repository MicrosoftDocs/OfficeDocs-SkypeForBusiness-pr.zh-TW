---
title: 移轉程序
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 商務用 Skype Server 2019 的建議和支援的遷移程式是並列式遷移。 本主題說明應使用並存移轉的原因，並包含共存測試的相關資訊。
ms.openlocfilehash: 2343e3d6dd7eadbcfbf2b900d51594253e22f933
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752635"
---
# <a name="migration-process"></a>移轉程序

商務用 Skype Server 2019 的建議和支援的遷移程式是並列式遷移。 本主題說明應使用並存移轉的原因，並包含共存測試的相關資訊。
  
## <a name="side-by-side-migration"></a>並存移轉

幾乎在每種移轉時，您都應該使用並存移轉路徑。 在並列式遷移中，您可以使用商務用 Skype Server 2019 和執行舊版的相對應伺服器來部署新的伺服器，然後將作業轉移至新的伺服器。 若要回復先前的版本，您只需要將作業移回原始伺服器。 請注意在這樣的情況下，任何與升級用戶端排定的新會議皆無法運作，導致用戶端也必須降級。
  
## <a name="coexistence-testing"></a>共存測試

在與舊版一起部署商務用 Skype Server 2019 後，部署代表商務用 Skype Server 2019 和上一版的共存測試狀態。 在此狀態中，請務必測試並確定服務已啟動、每個網台都可以受系統管理，且用戶端可與目前及舊版使用者通訊。 移轉所有使用者之前，請先了解每個部署的狀態並確定兩者皆正常運作，這點是非常重要的。 通常，共存測試階段會存在於整個商務用 Skype Server 2019 的試驗測試中。 舊版使用者會移至商務用 Skype Server 2019 一段時間，以確保應用程式相容性和功能正常運作。 在試驗測試之後，使用者和應用程式會移至商務用 Skype Server 2019 的實際執行版本，舊版集區和舊版本的應用程式就會終止。
  
