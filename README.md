# handle_enum_decodable

```swift
    struct Rating: Codable {
        let rating: Int?
        let content: String?
        
        enum CodingKeys: String, CodingKey {
            case rating
            case content
        }
        
        init(rating: Int?, content: String?) {
            self.rating = rating
            self.content = content
        }
        
        init(from decoder: Decoder) throws {
            let container: KeyedDecodingContainer<Sleep.Rating.CodingKeys> = try decoder.container(keyedBy: Sleep.Rating.CodingKeys.self)
            self.rating = try container.decodeIfPresent(Int.self, forKey: Sleep.Rating.CodingKeys.rating)
            self.content = try container.decodeIfPresent(String.self, forKey: Sleep.Rating.CodingKeys.content)
        }
        
    }
    
```
