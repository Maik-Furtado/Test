classDiagram
        namespace Domain_Entity {
        class Wallet {
            -Long id
            -String fullName
            -String cpfCnpj
            -String email
            -String password
            -BigDecimal balance
            +isTransferAllowedForWalletType() boolean
            +isBalanceEqualOrGreaterThan(value) boolean
            +debit(value)
            +credit(value)
        }
        class Transfer {
            -Long id
            -BigDecimal value
        }
        class WalletType {
            -Long id
            -String description
            +from(type) WalletType
        }
        class EWalletType {
            <<enumeration>>
            USER
            MERCHANT
        }
    }

    namespace Service {
        class WalletService {
            +createWallet(dto) Wallet
        }
        class TransferService {
            +transfer(dto) Transfer
        }
    }

    namespace Repository {
        class WalletRepository {
            <<interface>>
        }
        class WalletTypeRepository {
            <<interface>>
        }
        class TransferRepository {
            <<interface>>
        }
    }

    Wallet "1" --> "1" WalletType : has
    Transfer "1" --> "1" Wallet : sender
    Transfer "1" --> "1" Wallet : receiver

    WalletService --> WalletRepository
    WalletService --> WalletTypeRepository

    TransferService --> WalletRepository
    TransferService --> TransferRepository

    WalletType --> EWalletType
