```tsx
// form.tsx

🟢 - should be.
🟡 - should be, but there will instance to realigned it (e.g. mandatory parameters from or for other hooks)
🔴 - should be, but there will instance to realigned it (e.g. mandatory parameters from or for other hooks) or depends on design logic and perspective

const Form: React.FC<FormProps> = (props) => {
  const { prop } = props;

  // 🟢 hook style here
  const styles = useStyles({ isSample: true });

  // 🟡 hooks inside of the File, but there would be an instance that it will put on other line, (e.g. mandatory parameters from or for other hooks)
  const { useClick } = useButton();

  // 🟢 hooks from external dependencies
  const navigate = useNavigate();
  const matches = useMatches();

  // 🔴 hooks from util: util/config util/helper util/store
  // it can be put in any lines just below of the upper rules. it could be on top or below of states, effects or outside hooks
  // but the util/store should be here always, on top of rules below.
  const dispatch = useAppDispatch();
  const { user } = useAppSelector((state) => state.globalCommon);

  // 🟡 hooks outside of the file but same directory: hook.ts
  const { form, handleOnSave } = useForm();

  // 🟡 hooks outside of the File but same directory (with the consideration if nested directories)
  const { helper } = useFormMisc();

  // 🔴 hooks from util: @/util/helper/api
  // it can be put in any lines just below of the upper rules. it could be on top or below of states, effects or outside hooks

  // 🔴 useState()
  const [mode, setMode] = useState(theme.palette.mode);

  // 🔴 useEffect()
  useEffect(() => {
    setMode(theme.palette.mode);
  }, [theme.palette.mode]);

  // 🔴 event handlers
  const handleOnClick = (): void => {
    // your logic here
  };

  return <div />;
};

export default Form;
```
