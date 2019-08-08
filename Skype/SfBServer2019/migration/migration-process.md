---
title: 遷移程式
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 商務用 Skype Server 2019 的建議和支援的遷移程式是並排遷移。 本主題描述為什麼您應該使用並列移植, 同時還包含共存測試的相關資訊。
ms.openlocfilehash: 6ef8a70aa436663b7ff88723800375eeef620b6d
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36238083"
---
# <a name="migration-process"></a>遷移程式

商務用 Skype Server 2019 的建議和支援的遷移程式是並排遷移。 本主題描述為什麼您應該使用並列移植, 同時還包含共存測試的相關資訊。
  
## <a name="side-by-side-migration"></a>並行遷移

在幾乎所有的遷移中, 您都應該使用並行遷移路徑。 在並列式遷移中, 您可以使用商務用 Skype Server 2019 以及執行舊版的對應伺服器以及將作業轉移到新伺服器的方式, 來部署新的伺服器。 如果需要回滾到前一個版本, 您只需要將操作移回原始伺服器。 請注意, 在這種情況下, 使用升級後的用戶端排程的新會議將無法運作, 而且用戶端也必須降級。
  
## <a name="coexistence-testing"></a>共存測試

將商務用 Skype Server 2019 與早期版本並行部署之後, 部署代表商務用 Skype Server 2019 與舊版的共存測試狀態。 當處於這個狀態時, 請務必測試並確定服務已啟動、可管理每個網站, 而且用戶端可以與目前與舊版使用者通訊。 在遷移所有使用者之前, 請務必瞭解每個部署的狀態, 並確保每個部署都能正常運作且正常運作。 通常, 共存測試階段會在整個商務用 Skype Server 2019 的試驗測試中存在。 舊版使用者會在一段時間內移至商務用 Skype Server 2019, 以確保應用程式相容性及功能及功能正常運作。 先導測試之後, 使用者和應用程式會移至商務用 Skype Server 2019 的生產版本, 而舊版池和舊版本的應用程式就會停用。
  
