# BE 일관성 맞추기 프로젝트

## 어노테이션 순서

- 클래스 단: 스웨거 API 정보 -> @Slf4j -> 롬복 -> API(RestController -> RequestMapping) 중요한 것을 밑으로 (이렇게하죠)
  @Tag
  @ApiResponse
  @Slf4j
  @RequiredArgsConstructor
  @RestController
  @RequestMapping("/chats")
- 메소드 단:스웨거 API 정보(Operation -> ApiResponse) -> API
  @Operation
  @ApiResponse
  @GetMapping("/{party-id}")
- 메소드 필드: @PathVariable -> @RequestBody -> BindingResult
